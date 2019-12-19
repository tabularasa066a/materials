◆現行環境
[debug1]NewsFeed
[debug2]NewsFeed::ActiveRecord_Relation
[debug3]NewsFeed::ActiveRecord_Relation
[debug4]NewsFeed (重要：objectのクラス)
[debug5]Array
[debug6]NewsFeed # index.html.erbにおいて、news_feed.classを見た

◆旧環境
[debug3]WillPaginate::Collection
[debug4]NewsFeed (重要：objectのクラス)
[debug5]Array
[debug6]NewsFeed # index.html.erbにおいて、news_feed.classを見た


★ロガーをしこむ場所
1. news_feeds_controller.rbのindexメソッド
```r
  def index
    @news_feeds = NewsFeed.order(:position).paginate(:page => params[:page])
    respond_to do |format|
      format.html # index.html.erb
      format.xml  { render :xml => @news_feeds }
    end
    Rails.logger.error("[debug1]#{NewsFeed.new.class}")
    Rails.logger.error("[debug2]#{NewsFeed.order(:position).class}")
    Rails.logger.error("[debug3]#{NewsFeed.order(:position).paginate(:page => params[:page]).class}") # @news_feeds
  end
```

2. app/views/page/_position.html.erbの一番上
```r
  <% Rails.logger.error("[debug4]#{object.class}") %>
  <% Rails.logger.error("[debug5]#{Array(object).class}") %>
```

3. index.html.erb
```r
  <%- @news_feeds.each do |news_feed| -%>
    <tr class="line<%= cycle("0", "1") -%>">
      <% Rails.logger.error("[debug6]#{news_feed.class}") %>
      <td><%= move_position(news_feed) -%></td>
      <td><%= link_to h(news_feed.title), admin_news_feed_path(news_feed) -%></td>
      <td><%= link_to h(news_feed.url), news_feed.url -%></td>
      <td><%= link_to t('page.edit'), edit_admin_news_feed_path(news_feed) -%></td>
      <td><%= link_to t('page.destroy'), admin_news_feed_path(news_feed), :confirm => t('page.are_you_sure'), :method => :delete -%></td>
    </tr>
  <%- end -%>
```

★その他
```<%= object.first? ? image_tag('cross.png', :size => '16x16') : link_to(image_tag('arrow_up.png'), {:action => 'update', :position  => (object.position > 1 ? object.position - 1 : 1), :id => object.id}, :method => :put) -%>```

## object.positionで取得したデータの値は全てnilとなっており、これが影響する？
- これは現状関係ない。if文入る前のfirst?メソッドでつまづく

## 旧環境のクラスを見て、相違がなかったらacts_as_listの最新版をインストールし、旧版を削除してみる？

## Array(object)の出力値
[debug][#<NewsFeed id: 26, library_group_id: 1, title: "test", url: "https://www.google.co.jp/", body: nil, position: nil,
created_at: "2019-12-10 08:10:33", updated_at: "2019-12-10 08:10:33">]
- 要素一個の配列

## Array(object)[0].class = object.class = NewsFeed
◆現行環境
1. @news_feeds: NewsFeed::ActiveRecord_Relation
2. ```<%- @news_feeds.each do |news_feed| -%>```したときの news_feed: NewsFeed
3. move_positionで_position.html.erbに渡され object: NewsFeed
- order(:position)を作用させたことでNewsFeedがNewsFeed::ActiveRecord_Relationになった
- .eachを作用させたことでNewsFeed::ActiveRecord_RelationがNewsFeedに戻り、objectに渡されたので、objectがNewsFeedとなった。

## first?メソッドはacts_as_listのメソッド
- controller.rbにおいてNewsFeed.new.first?としたが、`undefined method 'first?' for #<NewsFeed:0x00007fac94663620>`
- class的に使えないことを意味する？
- You'll have a number of methods added to each instance of the ActiveRecord model that to which acts_as_list is added.
  (https://github.com/brendon/acts_as_list#instance-methods-added-to-activerecord-models)


##
- lib下のlibrary_group.rb消してからacts_as_list導入しない？？

[旧]
link_to(
  image_tag('arrow_up.png'), 
  {:action => 'update', :position  => (object.position > 1 ? object.position - 1 : 1), :id => object.id},
  :method => :put
  )
[新]


## routing
    admin_news_feeds GET    /admin/news_feeds(.:format)             admin/news_feeds#index
                     POST   /admin/news_feeds(.:format)             admin/news_feeds#create
 new_admin_news_feed GET    /admin/news_feeds/new(.:format)         admin/news_feeds#new
edit_admin_news_feed GET    /admin/news_feeds/:id/edit(.:format)    admin/news_feeds#edit
     admin_news_feed GET    /admin/news_feeds/:id(.:format)         admin/news_feeds#show
                     PATCH  /admin/news_feeds/:id(.:format)         admin/news_feeds#update
                     PUT    /admin/news_feeds/:id(.:format)         admin/news_feeds#update
                     DELETE /admin/news_feeds/:id(.:format)         admin/news_feeds#destroy

## ブランチ：`feature/Rss_feeds2`

##
`position_column` = @news_feed.position.to_i
`スコープ`：複数のクエリをまとめたメソッド
(例)
```ruby
class User < ApplicationRecrd
  ...
    # deletedカラムがfalseであるものを取得する
    scope :active, -> { where(deleted: false) }
    # created_atカラムを降順で取得する
    scope :sorted, -> { order(created_at: :desc) }
    # activeとsortedを合わせたもの
    scope :recent, -> { active.sorted }
  ...
end
```

```ruby
class UsersController < ApplicationController
  ...
  def index
    @users = User.recent
    # @users = User.where(deleted: false).order(created_at: :desc)
  end
  ...
end
```


## gem: acts_as_listの読み込み
1. `vendor/plugins/`下の`acts_as_list`は削除する
2. `acts_as_list`の`1.0.0`を入れる
3. モデルの機能を有効化する
