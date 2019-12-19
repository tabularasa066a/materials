- Rails.logger.error "[debug a]#{params.inspect}"
[debug a]<ActionController::Parameters {"bibmarcno"=>{"datatype"=>["[\"bibMarcNo\"]"], "TEXT"=>["TEXT"]}, "bibiden
tifier"=>{"datatype"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"bibIde
ntifier\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], "TEXT"=>["TEXT"]},
"title"=>{"value"=>["[\"＊平治物語\"]", "[\"\"]"], "transcription"=>["[\"fuke確認中\"]", "[\"\"]"]}, "alternative"=>{"value"=>["[\"alternative\"]"], "transcriptio
n"=>["[\"alternative\"]"]}, "series_title"=>{"value"=>["[\"series_title\"]"], "transcription"=>["[\"series_title\"]"]}, "uniform_title"=>{"value"=>["[\"uniform_ti
tle\"]"], "transcription"=>["[\"uniform_title\"]"]}, "responsibility"=>{"TEXT"=>["responsibility"]}, "volume_title"=>{"value"=>["[\"volume_title\"]"], "transcript
ion"=>["[\"volume_title\"]"]}, "volume"=>{"value"=>["[\"volume\"]"], "transcription"=>["[\"volume\"]"]}, "alternative_volume"=>{"value"=>["[\"alternative_volume\"
]"], "transcription"=>["[\"alternative_volume\"]"]}, "alternative_volume_title"=>{"value"=>["[\"alternative_volume_title\"]"], "transcription"=>["[\"alternative_v
olume_title\"]"]}, "creator"=>{"name"=>["[\"creator\"]"], "transcription"=>["[\"creator\"]"]}, "creator_alternative"=>{"TEXT"=>["creator_alternative"]}, "series_c
reator"=>{"TEXT"=>["series_creator"]}, "part_information"=>{"title"=>["[\"part_information\"]"], "transcription"=>["[\"part_information\"]"], "creator"=>["[\"part
_information\"]"]}, "edition"=>{"TEXT"=>["edition"]}, "edition_creator"=>{"TEXT"=>["edition_creator"]}, "publisher"=>{"name"=>["[\"publisher\"]"], "transcription"
=>["[\"publisher\"]"], "description"=>["[\"publisher\"]"], "location"=>["[\"publisher\"]"]}, "publicationplace"=>{"datatype"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"
[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"publicationplace\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], "TEXT"=>["publicationplace"]}, "date"=>{"TEXT"=>["a"]}, "created"=>{"TEXT"
=>["a"]}, "issued"=>{"TEXT"=>["2006-09-25"]}, "language"=>{"datatype"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"language\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\
\\"]\\\\\\\"]\\\"]\"]"], "TEXT"=>["language"]}, "description"=>{"TEXT"=>[",,,,,,"]}, "subject"=>{"value"=>["[\"subject\"]"], "transcription"=>["[\"subject\"]"]},
"extent"=>{"TEXT"=>["extent"]}, "materialtype"=>{"resource"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"materialtype\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\
\\\\\"]\\\"]\"]"], "label"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"
materialtype\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"]}, "publications
tatus"=>{"TEXT"=>["publicationstatus"]}, "publicationperiodicity"=>{"TEXT"=>["publicationperiodicity"]}, "spatial"=>{"TEXT"=>["spatial"]}, "modified"=>{"TEXT"=>["
modified"]}} permitted: false>

- Rails.logger.error "[debug b]#{params.permit!.to_hash.inspect}"
[debug b]
{
"bibmarcno"=>{"datatype"=>["[\"bibMarcNo\"]"], "TEXT"=>["TEXT"]}, 
"bibidentifier"=>{"datatype"=>["[\"[\\
\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"bibIdentifier\\\\\\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], "TEXT"=>["TEXT"]}, 
"title"=>{"value"=>["[\"＊平治
物語\"]", "[\"\"]"], "transcription"=>["[\"fuke確認中\"]", "[\"\"]"]}, 
"alternative"=>{"value"=>["[\"alternative\"]"], "transcription"=>["[\"alternative\"]"]}, "s
eries_title"=>{"value"=>["[\"series_title\"]"], "transcription"=>["[\"series_title\"]"]}, 
"uniform_title"=>{"value"=>["[\"uniform_title\"]"], "transcription"=>["[
\"uniform_title\"]"]}, 
"responsibility"=>{"TEXT"=>["responsibility"]}, 
"volume_title"=>{"value"=>["[\"volume_title\"]"], 
"transcription"=>["[\"volume_title\"]"]},
"volume"=>{"value"=>["[\"volume\"]"], "transcription"=>["[\"volume\"]"]}, "alternative_volume"=>{"value"=>["[\"alternative_volume\"]"], "transcription"=>["[\"alt
ernative_volume\"]"]},
"alternative_volume_title"=>{"value"=>["[\"alternative_volume_title\"]"], "transcription"=>["[\"alternative_volume_title\"]"]},
"creator"=>
{"name"=>["[\"creator\"]"], "transcription"=>["[\"creator\"]"]},
"creator_alternative"=>{"TEXT"=>["creator_alternative"]},
"series_creator"=>{"TEXT"=>["series_cre
ator"]}, 
"part_information"=>{"title"=>["[\"part_information\"]"], 
"transcription"=>["[\"part_information\"]"], 
"creator"=>["[\"part_information\"]"]}, 
"edition"=>{"TEXT"=>["edition"]},
"edition_creator"=>{"TEXT"=>["edition_creator"]},
"publisher"=>{"name"=>["[\"publisher\"]"], 
            "transcription"=>["[\"publisher\"]"],
            "description"=>["[\"publisher\"]"],
            "location"=>["[\"publisher\"]"]},
"publicationplace"=>{"datatype"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"publicationplace\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\
\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], 
                    "TEXT"=>["publicationplace"]}, 
"date"=>{"TEXT"=>["a"]}, 
"created"=>{"TEXT"=>["a"]}, 
"issued"=>{"TEXT"=>["2006-09-25"]}, 
"language"=>{"datatype"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\"language\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], 
            "TEXT"=>["language"]}, 
"description"=>{"TEXT"=>[",,,,,,"]}, 
"subject"=>{"value"=>["[\"subject\"]"], 
"transcription"=>["[\"subject\"]"]}, 
"extent"=>{"TEXT"=>["extent"]}, 
"materialtype"=>{"resource"=>["[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
\\"materialtype\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"], "label"=>["
[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"materialtype\\\\\\\\\\\\\\\\\\
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]"]}, "publicationstatus"=>{"TEXT"=>["publication
status"]}, 
"publicationperiodicity"=>{"TEXT"=>["publicationperiodicity"]}, 
"spatial"=>{"TEXT"=>["spatial"]}, 
"modified"=>{"TEXT"=>["modified"]}
}

- Rails.logger.error "[debug c]#{params[:resource].inspect}"
[debug c]
{
"bibmarcno_datatype"=>"[\"[\\\"bibMarcNo\\\"]\"]",
"bibmarcno"=>"TEXT", 
"bibidentifier_datatype"=>"[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"bibIdentifier\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]", "bibidentifier"=>"TEXT",
"title_value"=>"[\"[\\\"＊平治物語\\\"]\"]\r\n[\"[\\\"\\\"]\"]", "title_transcription"=>"[\"[\\\"fuke確認中\\\"]\"]\r\n[\"[\\\"\\\"]\"]", "alternative_value"=>"[\"[\\\"alternative\\\"]\"]", 
"alternative_transcription"=>"[\"[\\\"alternative\\\"]\"]", 
"series_title_value"=>"[\"[\\\"series_title\\\"]\"]", 
"series_title_transcription"=>"[\"[\\\"series_title\\\"]\"]", 
"uniform_title_value"=>"[\"[\\\"uniform_title\\\"]\"]", 
"uniform_title_transcription"=>"[\"[\\\"uniform_title\\\"]\"]", "responsibility"=>"responsibility", 
"volume_title_value"=>"[\"[\\\"volume_title\\\"]\"]", 
"volume_title_transcription"=>"[\"[\\\"volume_title\\\"]\"]", 
"volume_value"=>"[\"[\\\"volume\\\"]\"]", 
"volume_transcription"=>"[\"[\\\"volume\\\"]\"]", 
"alternative_volume_value"=>"[\"[\\\"alternative_volume\\\"]\"]", "alternative_volume_transcription"=>"[\"[\\\"alternative_volume\\\"]\"]", "alternative_volume_title_value"=>"[\"[\\\"alternative_volume_title\\\"]\"]", "alternative_volume_title_transcription"=>"[\"[\\\"alternative_volume_title\\\"]\"]", "creator_name"=>"[\"[\\\"creator\\\"]\"]", 
"creator_transcription"=>"[\"[\\\"creator\\\"]\"]", "creator_alternative"=>"creator_alternative", 
"series_creator"=>"series_creator", 
"part_information_title"=>"[\"[\\\"part_information\\\"]\"]", "part_information_transcription"=>"[\"[\\\"part_information\\\"]\"]", "part_information_creator"=>"[\"[\\\"part_information\\\"]\"]", 
"edition"=>"edition", 
"edition_creator"=>"edition_creator", 
"publisher_name"=>"[\"[\\\"publisher\\\"]\"]", 
"publisher_transcription"=>"[\"[\\\"publisher\\\"]\"]", 
"publisher_description"=>"[\"[\\\"publisher\\\"]\"]", 
"publisher_location"=>"[\"[\\\"publisher\\\"]\"]", 
"publicationplace_datatype"=>"[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"publicationplace\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]", "publicationplace"=>"publicationplace", 
"date"=>"a", 
"created"=>"a", 
"issued"=>"2006-09-25", 
"language_datatype"=>"[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"language\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]", "language"=>"language", 
"description"=>",,,,,,", 
"subject_value"=>"[\"[\\\"subject\\\"]\"]", 
"subject_transcription"=>"[\"[\\\"subject\\\"]\"]", 
"extent"=>"extent", 
"materialtype_resource"=>"[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"materialtype\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]", "materialtype_label"=>"[\"[\\\"[\\\\\\\"[\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"[\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"materialtype\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\"]\\\\\\\\\\\\\\\"]\\\\\\\"]\\\"]\"]", "publicationstatus"=>"publicationstatus", "publicationperiodicity"=>"publicationperiodicity", 
"spatial"=>"spatial", 
"modified"=>"modified"
}

[debug c]<ActionController::Parameters 
{
    "title"=>{
        "value"=>["[\"[\\\"[\\\\\\\"ほげほげ［方言］ (日本方言大辞典)\\\\\\\"]\\\"]\"]"],
        "transcription"=>["[\"[\\\"[\\\\\\\"ほげほげ\\\\\\\"]\\\"]\"]"]
        }, 
    "description"=>{"TEXT"=>["日本方言大辞典"]}, 
    "subject"=>{
        "value"=>["[\"[\\\"[\\\\\\\"ほげほげ\\\\\\\"]\\\"]\"]"], 
        "transcription"=>["[\"[\\\"\\\"]\"]"]
        }, 
    "materialtype"=>{
        "resource"=>["[\"[\\\"ReferenceInformation\\\"]\"]"], 
        "label"=>["[\"[\\\"参考情報\\\"]\"]"]
    }
} permitted: false>

"individuals"=>
{"0"=>{
    "item_no"=>["I022000740"], 
    "library_code"=>["0000"], 
    "old_library_code"=>["4211"], 
    "call_number"=>["５９９．０／カ／"], 
    "holding_issue"=>[""], 
    "absent_issue"=>[""], 
    "availability"=>["帯出可"], 
    "identifier"=>["1009610040308", "1112642837"], 
    "identifier_datatype"=>["somokuBibID", "somokuSubID"], 
    "description"=>["配置場所 : 閉架図書"], 
    "newspaper_id"=>[""]
    }, 
    "delete_flag"=>["2"], 
"1"=>{"item_no"=>["I011317534"], "library_code"=>["122
1"], "old_library_code"=>["1221"], "call_number"=>[""], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["帯出可"], "identifier"=>["1000010451419"],
"identifier_datatype"=>["somokuBibID"], "description"=>["配置場所 : 開架"], "newspaper_id"=>[""]}, "2"=>{"item_no"=>["I024849560"], "library_code"=>["0121"], "old
_library_code"=>["0121"], "call_number"=>["５９９／カ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["帯出可"], "identifier"=>["1001000940521",
"0017649112"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "3"=>{"item_no"=>["I026545731"], "library_code"=
>["2321"], "old_library_code"=>["2321"], "call_number"=>["Ｎ５９９／９２７／"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出可"], "identifi
er"=>["1009610022467", "0232936971"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "4"=>{"item_no"=>["I05110
5444"], "library_code"=>["1811"], "old_library_code"=>["1811"], "call_number"=>["599-ｶﾐｵ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出用"
], "identifier"=>["1103477258", "1012599872"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["所蔵場所 : 集密書庫"], "newspaper_id"=>[""]
}, "5"=>{"item_no"=>["I052584907"], "library_code"=>["2721"], "old_library_code"=>["2721"], "call_number"=>[""], "holding_issue"=>[""], "absent_issue"=>[""], "ava
ilability"=>[""], "identifier"=>["0000535843", "0000535843"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "
6"=>{"item_no"=>["I058602255"], "library_code"=>["0411"], "old_library_code"=>["0411"], "call_number"=>["599.04/1996.5"], "holding_issue"=>[""], "absent_issue"=>[
""], "availability"=>["貸出・閲覧可"], "identifier"=>["5010316888", "1005098734"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["配置場
所 : 一４：一般書庫４"], "newspaper_id"=>[""]}, "7"=>{"item_no"=>["I059032282"], "library_code"=>["2011"], "old_library_code"=>["2011"], "call_number"=>["599.04/ｶ
ﾄ/"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>[""], "identifier"=>["1009610024591", "0112230107"], "identifier_datatype"=>["somokuBibID", "so
mokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "8"=>{"item_no"=>["I060263332"], "library_code"=>["2411"], "old_library_code"=>["2411"], "call_number"=>[
"599.0-ｶ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["持出可能"], "identifier"=>["1101250255", "113251524"], "identifier_datatype"=>["somokuB
ibID", "somokuSubID"], "description"=>["所蔵場所 : 閉架（一般）"], "newspaper_id"=>[""]}, "9"=>{"item_no"=>["I060942350"], "library_code"=>["3511"], "old_library_
code"=>["3511"], "call_number"=>["599/M 6"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出・閲覧可"], "identifier"=>["9610062438", "00516379
5"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "10"=>{"item_no"=>["I077035355"], "library_code"=>["2511"]
, "old_library_code"=>["2511"], "call_number"=>["3-5990-ｶ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出・閲覧可"], "identifier"=>["101297
7", "126596683"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "11"=>{"item_no"=>["I080771033"], "library_co
de"=>["2722"], "old_library_code"=>["2722"], "call_number"=>["599.04/ｶ/8"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>[""], "identifier"=>["100
0000355185", "601410350"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>[""], "newspaper_id"=>[""]}, "12"=>{"item_no"=>["I082493626"], "l
ibrary_code"=>["2611"], "old_library_code"=>["2611"], "call_number"=>[" 59/ｶ22/"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出可"], "ident
ifier"=>["B10476592", "1106758145"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["自動書庫"], "newspaper_id"=>[""]}, "13"=>{"item_no"=>
["I083314358"], "library_code"=>["4611"], "old_library_code"=>["4611"], "call_number"=>["599.0/ｶ96"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=
>["貸出可能資料"], "identifier"=>["9610020594", "0211005822"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["配置場所 : 奄美書庫１層（一
般）"], "newspaper_id"=>[""]}, "14"=>{"item_no"=>["I084463970"], "library_code"=>["4411"], "old_library_code"=>["4411"], "call_number"=>["599-2006"], "holding_iss
ue"=>[""], "absent_issue"=>[""], "availability"=>["帯出可"], "identifier"=>["1106033609", "00012945804"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "
description"=>["所蔵場所 : 一般資料室"], "newspaper_id"=>[""]}, "15"=>{"item_no"=>["I085016337"], "library_code"=>["3611"], "old_library_code"=>["3611"], "call_nu
mber"=>["599-ｶﾐ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["貸出可能"], "identifier"=>["1100392243", "00105511425"], "identifier_datatype"=>
["somokuBibID", "somokuSubID"], "description"=>["所蔵場所 : 書庫一般"], "newspaper_id"=>[""]}, "16"=>{"item_no"=>["I085905130"], "library_code"=>["1121"], "old_li
brary_code"=>["1121"], "call_number"=>["599"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>[""], "identifier"=>["780001", "01190063857"], "identi
fier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["配置場所 : 自動書庫"], "newspaper_id"=>[""]}, "17"=>{"item_no"=>["I088879201"], "library_code"=>[
"2221"], "old_library_code"=>["2221"], "call_number"=>["599.04-ｶ"], "holding_issue"=>[""], "absent_issue"=>[""], "availability"=>["持出可能"], "identifier"=>["110
1067662", "111732531"], "identifier_datatype"=>["somokuBibID", "somokuSubID"], "description"=>["所蔵場所 : 書庫"], "newspaper_id"=>[""]}}}
