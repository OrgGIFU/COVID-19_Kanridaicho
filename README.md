**岐阜県新型コロナ管理台帳システム**

**1.「岐阜県新型コロナ管理台帳システム」とは**

オープンソースのWebデータベース型ローコード開発プラットフォームの「[プリザンダー](https://pleasanter.org/)」を利用して構築したシステムとなります。本システムのソーソコード等を活用することで、新型コロナの陽性患者に関するERSYS等と連携や、受付から療養終了まで疫学調査等を行う職員の業務を効率化することが可能となります。

本取組みは[自治体通信オンライン](https://www.jt-tsushin.jp/interview/jt42_ctcs/)にて紹介をいただきました。
また、[第一回プリザンター・スクリプト・コンテスト](https://www.ceccs.co.jp/)にて特別賞をいただきました。

画面イメージ＜一覧表示＞

![](28703f33-663a-4b60-bbc3-f13106a47c5f.001.png)

画面イメージ＜明細1>

![](28703f33-663a-4b60-bbc3-f13106a47c5f.002.png)

画面イメージ＜明細2>

![](28703f33-663a-4b60-bbc3-f13106a47c5f.003.png)

**2.ライセンス形態：**

AGPL (Affero General Public License) 　←　調査中！！

**3.本リポジトリの利用対象者（想定）：**

(1) 疫学調査等を行う都道府県職員

運用イメージは「資料３業務フロー図（2022/8/18時点）」を参照願います。

(2)プリザンダーのスクリプト等のソースコード利用者

**4.サイトマップ：**

├─ README.md            	          // このドキュメント

├─ 01\_資料1\_スクリプト説明書.pdf        // 概要　システム概要、開発ポイント・補足事項

├─ 02\_資料2\_画面説明.pdf	     // 画面説明

├─ 03\_資料3\_業務フロー.pdf	    // 業務フロー図

├─ 04\_資料4\_イベント関連図.pdf    	  // イベント関連図

├─ 05\_資料5\_項目定義一覧.pdf    	   // 項目定義

├─ 20220818版\_2022\_09\_02 18\_56\_08.json　　//テーブル等の設定情報等を格納したエクスポートファイル（JSON形式）

└─ LISENCE               	         //　ライセンス

**5.開発・動作環境：**

(1) プリザンダー:1.3.9.0 （有償版　Enterprise Edition）

　　・無償版の Community Edition　の場合、項目数が不足しているため、ほとんどの機能が動作しません。
  
　　・インターネット上にある　プリザンダー.net環境の無償版では、スタイル・スクリプト・サーバスクリプトが動作しないため本機能は動作しません。    

(2) Pleasanter to Excel（有償ソフト） 

　　・格納されているデータをExcelの個票印刷などに利用するため利用します。画面から印刷ボタンで動作します。本ソフトウェアが無くても基本動作は問題ありません。

(3) データベース：SQL Server std 2019（有償版） 

　　・無償版のSQL Server Expressでも動作しますが、データ格納容量が10GBと制限があるため有償版に切り替えています。 

**6.使い始める方法：**

⓵ プリザンダー環境を構築する。

　　・構築の詳細はプリザンダーのユーザマニュアル（セットアップ）を参照ください。

⓶ Pleasanter to Excelソフトのインストール・セットアップ（無くても基本動作は可能）

⓷ プリザンダーの利用者アカウントを作成する。

　　・ログインID：Administrator　      役割：システム全体の管理者。
 
　　・ログインID：ichi　　　　　　      役割：データ登録やデータ管理を行います。
 
　　・ログインID：gifuhc               役割：代表的な一般ユーザで、データ入力を行います。

⓸ プリザンダーにログインし「サイトパッケージのインポート」操によりエクスポートファイルを取込む。

⓹ 個別設定値の編集

　テーブル管理 > スクリプト　＞　タイトル：　定数\_エディタ
 
　各メールアドレス：xxx@pref.gifu.lg.jp
 
　システムURL: const siteUrl = "https://daicho-naibu-kantai.rentai.local/items/";
 
　症例情報マスタのサイトID：const siteId = 569119;　（設定しなくても基本動作は可能）
 
　住所マスタのサイトID :const siteId\_zipCode = 201852;　（設定しなくても基本動作は可能）

⓺ 動作確認

**7.お問い合わせ等：**

(1) 本システムは予告なくアップグレードすることがあります。

(2) 本システムの障害があれば対応いたしますが、要望等はお受けすることができません。

　多くの疑問点は、[プリザンダーのユーザマニュアル](https://pleasanter.org/manual)と利用者のWebアプリ開発のナレッジにより解決します。
 
(3) プリザンダーの導入・開発に関して伴走支援をいただきました。

　導入にあたって伴走支援・機能カスタマイズ等の対応をいただける業者をお探しの方は、ご連絡願います。
 
　　[CTCシステムマネジメント株式会社（略称CTCS）](https://www.ctcs.co.jp/casestudy/detail/8/)

以上
