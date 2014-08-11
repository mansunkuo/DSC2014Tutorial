# 安裝說明

1. 請執行`R.version`檢查R 的版本。本次課程中需要3.1版本以上的R。如果是3.0的版本，安裝時會看到`package ‘DSC2014Tutorial’ is not available (for R version 3.0.2)`。
2. 請依據不同的OS在R console貼上下列script。如果有錯誤訊息，請參考最後的Q&A

## Windows

```r
install.packages('DSC2014Tutorial', repo = c('http://taiwanrusergroup.github.io/R', "http://cran.csie.ntu.edu.tw"), type = 'win.binary')
```

## Ubuntu

請先安裝以下Ubuntu套件:

```
sudo apt-get install libcurl4-openssl-dev libxml2-dev
```

再在R底下執行

```r
install.packages('DSC2014Tutorial', repo = c('http://taiwanrusergroup.github.io/R', "http://cran.csie.ntu.edu.tw"), type = 'source')
```

## Mac

請Mac User執行以下的Script:

```r
deps <- available.packages("http://taiwanrusergroup.github.io/R/src/contrib")[1,"Imports"]
pkgs <- strsplit(gsub("\\s", "", deps), ",")[[1]]
for(i in seq_along(pkgs)) {
  # You can change your favorite repository
  if (require(pkgs[i], character.only = TRUE)) next
  install.packages(pkgs[i], repo = "http://cran.csie.ntu.edu.tw")
}
install.packages('DSC2014Tutorial', repo = 'http://taiwanrusergroup.github.io/R', type = 'source')
```

## Q&A

- `ERROR: dependencies ‘wordcloud’, ‘gridExtra’ are not available for package ‘DSC2014Tutorial’`
    - 請貼上MAC上安裝套件的script，應可安裝所有相依套件。
    - 如果錯誤訊息依舊，應是某個套件安裝失敗。請將錯誤訊息回報至<https://github.com/TaiwanRUserGroup/DSC2014Tutorial/issues>
- `package ‘DSC2014Tutorial’ is not available (for R version 3.0.2)`
    - 請更新R到3.1以上的版本。

# 投影片

```r
library(DSC2014Tutorial)
slides("Basic")
slides("ETL")
slides("DataAnalysis")
slides("Visualization2")
slides("Visualization3")
```
