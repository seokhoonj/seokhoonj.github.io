---
layout: post
title: R openxlsx package를 이용한 엑셀 문서 작업
category: R
tags: [R, openxlsx, 엑셀]
published: true
comments: true
---

R openxlsx package를 이용한 엑셀 문서 작업
---

간단한 데이터 분석을 하고 나서 자료는 주로 마크다운 문서로 작성하고 있지만,  
엑셀로 분석을 하시는 분들이 많다보니, 데이터와 Plot을 엑셀에 저장하여 제공하는 경우가 꽤 있다.  
이를 위해 openxlsx 패키지를 이용하여,  
1. 시트생성
2. 각 시트마다 데이터와 plot 삽입
  
등의 작업을 수 있는 함수를 간단하게 개발해 보았다.  


``` r

#============================
#   create 
# , sheetnames (vector)
# , list_of_dataframe (list)
# , list_of_plot (list)
#============================
sheetnames<- c("meta"
             , "Sheet1"
             , "Sheet2"
             , "Sheet3"
             , "Sheet4"
             , "Sheet5"
             , "Sheet6"
)

ls_of_df <- list(meta
               , df_01
               , df_02
               , df_03
               , df_04
               , df_05
               , df_06
)

ls_of_plt <- list(NULL
                , p_01
                , p_02
                , p_03
                , p_04
                , p_05
                , p_06
)

#============================
# make an excel file function
#============================
mkxl <- function(filename, sheetnames, ls_of_df, ls_of_plt) {
  # create a workbook
  wb <- createWorkbook()
  
  # make sheets and insert data & plots
  for (i in seq_along(sheetnames)) {
    addWorksheet(wb, sheetnames[i], gridLines = FALSE)
    writeData(wb, sheetnames[i], ls_of_df[[i]], startCol = 1, startRow = 1, xy = NULL)
    if (sheetnames[i] != "meta") {
      print(ls_of_plt[[i]])
      insertPlot(wb, sheetnames[i], width = 12, height = 8, xy = NULL
               , startRow = 2, startCol = 10, fileType = "png", units = "in", dpi = 300)
    }
  }
  # save a workbook
  saveWorkbook(wb, filename, overwrite = TRUE)
}

mkxl(filename = "sample.xlsx", sheetnames = sheetnames, ls_of_df = ls_of_df, ls_of_plt = ls_of_plt)
```

to be updated...  
