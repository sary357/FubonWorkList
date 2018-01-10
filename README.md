## Objectives
- list down what I have done in Taipei Fubon Bank.

## Shared Folders
- 在我電腦上面有設定兩個分享資料夾

| 電腦路徑 | 分享的人 or Group |
| D:\ | |
| D:\ | |

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
