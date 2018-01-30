## Objectives
- list down what I have done in Taipei Fubon Bank.

## Shared Folders
- 在我電腦上面有設定兩個分享資料夾

| 電腦路徑 | 分享的人 or Group | 原由 |
|--|--|--|
| D:\資料分析應用科 | 資料平台及分析部資料分析應用科+資料平台及分析部資料治理科 | 一般分享用 |
| D:\客服營管科 | 個人金融總處個金客服部客服營管科+ Arthur Lee + Fu-Ming Tsai | 執行與 IconTek 之 PoC, 上傳營管科所錄的錄音檔案 |

## 相關專案
### Import 金腦科技
- 目前都是在 T_FUMINGTSAI 帳號下面
- 資料表格關係

| 表格名稱 | 用途 |
| COMPANY_LOG1| 公司基本資料 |
| PPTRQ_LOG1 | 全國動產 |
| TRADE_LOG1 | 國貿局_基本資料 |
| TRADE_INTERVAL_LOG1| 國貿局_級距資料 |

### 在 AWS 上面設定 RDS
- URL: https://github.com/sary357/fubon_aws_rds
- 目的: 可以讓資料部同事很方便的存取政府公開資訊
- P.S 
1. 需要由 Fu-Ming Tsai 告知資料庫密碼才可以使用
2. 目前是使用 sary357@yahoo.com.tw 登入, 刷的也是 Fu-Ming Tsai 的信用卡 :-)

### 使用 Neo4j 呈現 M+ 紅包分析資訊 
- URL: https://bitbucket.org/sary357/mplus_analysis_neo4j
- 目的: 由於 neo4j 很適合呈現`關係`, 而在 M+ 的紅包剛好用這個可以很好的呈現
- 更多內容: https://bitbucket.org/sary357/mplus_analysis_neo4j
- P.S 需要由 Fu-Ming Tsai 在 bitbucket 上面設定分享才能夠看到

### 安裝 Neo4J host
- URL: https://bitbucket.org/sary357/fubon_neo4j
- 說明安裝 neo4j 的注意事項
- P.S 需要由 Fu-Ming Tsai 在 bitbucket 上面設定分享才能夠看到

### 解析 Table 的血緣分析表
- URL: https://github.com/sary357/antlr-grammer-v4
- 是用來解析 PL/SQL 檔案使用, 其中
```
ConvertSQLFileEncoding.java: 轉換編碼格式, 由於原始檔案有可能是 Big5 編碼, 但是 Antlr 解析 Big5 一直有問題, 所以就先將 SQL檔案轉換成 UTF-8 再進行解析
PlsqlTableRelationParser.java: 專門解析 Table 之間的關係, 並畫在 neo4j 上面
PlsqlTableScanner.java: 跟 PlsqlTableRelationParser.java 很像, 差別只在於 PlsqlTableRelationParser.java 不會顯示 Temp table, 但是 PlsqlTableScanner.java 會
PlsqlColumnTableRelationParser.java: 專門解析 Table 中將同名的 Column 之間的關係在 Neo4j 上面串起來, 並畫在 neo4j 上面

```
- 更多內容可以參考: https://github.com/sary357/antlr-grammer-v4/tree/master/plsql

### IconTek 相關 Script
- 在 172.16.247.88 的 /home/sary357/icontek 中
- 進到 /home/sary357/icontek 中, 會看到下列目錄

```
sary357@TPEBNKFISCUBNT:~/icontek$ ls
20171117AM  20171120AM  20171121  20171127AM  20171129AM  tools
20171117PM  20171120PM  20171123  20171127PM  20171129PM  verification

```
- 目錄解說
  - tools
    - rename.py: 由於上傳的檔案有的時候檔名會不符合 IconTek 需求, 所以寫了這個 python 檔案, 使用方式: `python3 rename.py 目錄名稱 原始想要改的檔案名 想要改成怎樣的檔案名稱`, eg:  `python3 rename.py CC308_協助改檔名/ DEFAULT default` 是指要將 CC308_協助改檔名 這個目錄下面所有檔名帶有 DEFAULT 的檔案, 改成檔名帶有 default 的檔案
    - fileUpload.sh: 實際上傳到 IconTek 的 bash script
  - verification: 沒有使用了, 直接忽略即可
  - 年月日[AM/PM]: 代表每個時間點上傳的音檔, eg: 20171117AM 代表是 2017 年 11 月 17 日早上所傳到 IconTek 的檔案
- 其他資訊
  - Icontek 機器學習介面：https://vdev2.icontek.com:18010/secure/response/report   (login:  admin/xxxx), 需要用個人電腦登入，公司電腦需申請開通防火牆
  - 報表位置：https://vdev2.icontek.com:18010/report/

### 安和分行 wifi 訊號分析 
- URL: https://github.com/sary357/wifi_signal_analysis
- 目的: 是將 Conrad 整理好的資料做簡單呈現及分析
- 檔案說明: 有兩個檔案, SimpleTest.ipynb 和 SimpleTest2.ipynb, 兩者差別僅在是否過濾待少於10分鐘的 MAC address, 可以直接 load 到 Juypter 看分析結果

### Wherehows Docker Image
- 檔案位置: 172.16.247.88 的 /opt/Wherehows_20170915.tar
- 說明: Wherehows 是 LinkedIn 的一個project, 更多資訊可以參考 `https://github.com/linkedin/WhereHows`, /opt/Wherehows_20170915.tar 是我嘗試將 Wherehows 的 Docker image 檔案下載並啟動看看, 但可惜雖然可以啟動, 但不知道帳號密碼, 無法登入

### 商工資料分析
- URL: https://github.com/sary357/SimpleWebCrawler
- 檔案說明:
  - FindbizCrawler.py: 拿公司統編查詢 http://findbiz.nat.gov.tw/fts/query/QueryList/queryList.do , 但是商工登記有時會拿不到資料,  所以後來都用 Ronny Wang (http://company.g0v.ronny.tw) 的資料了
  - RonnyGovDataCrawler.py: 拿公司統編查詢 http://company.g0v.ronny.tw/, 比較穩定, 可以多多利用

### 資料服務 (只有投影片)
- 分享資料夾路徑: `\\172.17.22.181\資料分析應用科\暫存區\資料服務_20170828_v1.pptx`
- 概念: 想要將整理好的資訊用近似即時的方式傳給需要的人, 並用 AWS 的服務來試看看

### 建議的工具/套件清單
- URL: https://github.com/sary357/PackageList
- 目的: 是 Michael 希望我這邊可以列出可能會用到的工具/套件清單, 所以就整理在這邊, 後來 Conrad 也增加了 `Open Source Software inventory management` 章節, 補充說明如何管理 Open source 的軟體規則

### Google photo
- 我用我的 Google 帳號在 Google Photos 建立了一個 `資料平台及分析部` 的相簿, 也設定權限為只要看到這個相簿的人, 都可以上傳照片, 就請大家自由上傳照片了

### AWS RDS
- AWS Console: https://console.aws.amazon.com/console/home
- 我的 `sary357@yahoo.com.tw` 申請了 AWS RDS, 後端是選用 PostgreSQL, 免費使用期限 `(AWS Free Tier)` 到 2018 年 12 月為止, 預計會在 2018/11/30 停下這個服務, 目前是只有放政府公開資料在這邊

### FubonRD101
- URL: https://github.com/sary357/FubonRD101
- 目的: 這邊是放跟新人有關的資訊, 主要是給我自己看, 裡面包含權限設定, 計程車資, 電話,..., 等資料可供參考

### References
- TBD 



