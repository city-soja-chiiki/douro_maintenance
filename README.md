# 道路維持管理台帳保守　掲示板  
　[【アイ・サポート】](http://www.isupport.co.jp/company.html)

### 運用ルール  
　ISSUES の　CLOSE　は，OPEN　した者が行うこと。  
### システム概要
 1. 管理用プロジェクトファイル等  
 \\soja\総社市\道路・水路台帳システム\chiiki-iji  

 1. 管理データベース  
・PostgreSQL 管理データ(host=soja.gis-cdn.net)  
　維持管理データベース本体  
　　dbname='lizmap'  
　　table="public"."road_maintenance"  
　　table="public"."道路パトロール"

1. システム環境  
現在対応しているQGISバージョンは3.22  
3.28は未対応  (2023-06-26現在)  
　\\soja\総社市\QGIS\yr-qgis-portable-launcher  
　旧バージョンのランチャーを利用して起動  
　今回は，　QGIS3.22.16.bat　を利用  
　![Alt text](image/QGIS%E3%83%A9%E3%83%B3%E3%83%81%E3%83%A3%E3%83%BCBAT.png)  

### 作業手順概要
1. マニュアル
　　PostGISのアカウント等は  
　　\\soja\総社市\マニュアル\LIZMAP管理者マニュアル.docx  
　　QGIS-POSTGRE接続.xml　・・・「データソースマネージャ　＞　読み込み」   
　　![Alt text](image/%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3.png)
1. 作業用ローカルファイルのデータ更新  
　・最新データはファイルは，PostGIS環境のデータベースです。このデータベースは，LIZMAPより編集可能であり，定期更新の後に，WEBから更新されている可能性があるので注意してください。  
　PostGISのアカウント等は  
　　\\soja\総社市\マニュアル\LIZMAP管理者マニュアル.docx  
　　　QGIS-POSTGRE接続.xml　を使うと便利です。  
　・編集用ローカルファイルは  
　　2023-06-26現在のファイル保存先は  
　　\\soja\総社市\道路・水路台帳システム\chiiki-iji\道路パトロール作業用.gpkg  
　　レイヤ「道路パトロール作業用」を 編集して下さい。  
　　![Alt text](image/%E4%BD%9C%E6%A5%AD%E3%83%AC%E3%82%A4%E3%83%A4.png)

1. 作業用ローカルファイルのデータ編集  
　・基本的にデータの削除はしないでください。  
　・時間管理　from　to　で行ております。  
　　　属性：取得年月日，消去年月日にて表示の制御を行っております。  
　　　設定当日になったら自動的に表示が切り替わります。  
　　　![Alt text](image/%E5%B1%9E%E6%80%A7.png)

1. PostGIS環境へ  
　・プロセシングツールボックス　PostgreSQLへ出力　を用いる。
　　　　
1. プロジェクトファイルの更新  
　・区域更新等があった場合は，適宜バリューマップを更新のこと    
　　その他必要に応じて更新のこと。  
　　![Alt text](image/%E9%81%93%E8%B7%AF%E7%B6%AD%E6%8C%81%E7%AE%A1%E7%90%86%EF%BC%8D%E5%8C%BA%E5%9F%9F%EF%BC%8D%E3%83%90%E3%83%AA%E3%83%A5%E3%83%BC%E3%83%9E%E3%83%83%E3%83%97.png)

1. プロジェクトファイルのFTP転送  
　・プロジェクトファイルの変更を伴う場合はLIZMAPプラグインにより編集を行った後にFTP転送を行うこと。  