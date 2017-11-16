---
title: "Visual Studio용 R 도구를 사용한 R Markdown | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac955b2-b6e1-4d32-b1a4-2882c93311fc
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: e3d9ee899c9ed82cacfd9466412bacfea6b8c5e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-r-markdown-documents"></a>R Markdown 문서 만들기

[R Markdown](https://rmarkdown.rstudio.com/)은 R의 분석을 고품질 문서, 보고서, 프레젠테이션 및 대시보드로 전환하는 문서 형식입니다.

RTVS(Visual Studio용 R 도구)는 R Markdown 항목 템플릿, 편집기 지원(편집기 내에 R 코드용 IntelliSense 포함) 및 파일 생성 기능을 제공합니다.

R Markdown을 사용하려면:

1. Visual Studio를 닫습니다.
1. (한 번만 실행) [pandoc.org](http://pandoc.org/installing.html)에서 `pandoc`를 설치합니다.
1. Visual Studio를 다시 시작합니다(pandoc 설치를 선택해야 함).
1. `knitr` 및 `rmarkdown` 패키지를 설치합니다([대화형 창](interactive-repl.md)에서 수행할 수 있음).

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. 새 R Markdown 파일을 만들려면 **파일 > 새로 만들기** 메뉴 명령을 사용하고 목록에서 **R Markdown**을 선택하거나, 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **R Markdown 추가**를 선택합니다(또는 **추가 > 새 항목...**을 선택하고 목록에서 **R Markdown**을 선택).

1. 새 파일의 기본 콘텐츠는 다음과 같습니다.

    ~~~markdown
    ---
    title: "Untitled"
    output: html_document
    ---
    
    This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and Microsoft Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.
    
    When you click the **R Tools | Publish | Preview** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:
    
    ```{r}
    summary(cars)
    ```
    
    You can also embed plots, for example:
    
    ```{r, echo=FALSE}
    plot(cars)
    ```
    
    Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
    
    ~~~

1. 편집하는 동안 언제든지 편집기를 마우스 오른쪽 단추로 클릭하고 HTML, PDF 및 Microsoft Word 옵션이 포함된 **미리 보기**를 선택합니다. 이 미리 보기에서 파일을 선택한 형식에 대해 적절하게 저장할 수 있습니다.
