## Objectives
- list down what I have done in Taipei Fubon Bank.

## Shared Folders
- 在我電腦上面有設定兩個分享資料夾

| 電腦路徑 | 分享的人 or Group | 原由 |
|--|--|--|
| D:\資料分析應用科 | 資料平台及分析部資料分析應用科+資料平台及分析部資料治理科 | 一般分享用 |
| D:\客服營管科 | 個人金融總處個金客服部客服營管科+Arthur Lee + Fu-Ming Tsai | 執行與 IconTek 之 PoC |

## 相關專案
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
