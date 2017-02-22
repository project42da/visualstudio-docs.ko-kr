---
title: "방법: XML 편집기에서 XSLT 변환 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
caps.latest.revision: 2
caps.handback.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: XML 편집기에서 XSLT 변환 실행
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

XML 편집기에서 XSLT 스타일시트를 XML 문서에 연결하고 변환을 수행하며 출력을 볼 수 있습니다.XSLT 변환의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.  
  
 **Output** 속성은 출력에 대한 파일 이름을 지정합니다.**Output** 속성이 비어 있으면 임시 디렉터리에 파일 이름이 생성됩니다.파일 확장명은 스타일시트에 있는 `xsl:output` 요소를 기반으로 하며 .xml, .txt 또는 .htm일 수 있습니다.  
  
 **Output** 속성이 .htm 또는 .html 확장명을 가진 파일 이름을 지정할 경우 [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Internet Explorer를 사용하여 XSLT 출력을 미리 볼 수 있습니다.다른 모든 파일 확장명은 [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Visual Studio에서 선택한 기본 편집기를 사용하여 열립니다.예를 들어, 파일 확장명이 .xml인 경우 Visual Studio에서는 XML 편집기를 사용합니다.  
  
### XML 문서에서 XSLT 변환을 실행하려면  
  
1.  XML 편집기에서 XML 문서를 엽니다.  
  
2.  XSLT 스타일시트를 XML 문서에 연결합니다.  
  
    -   XML 문서에 `xml-stylesheet` 처리 명령을 추가합니다.예를 들어, 문서 프롤로그에 다음 `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>` 줄을 추가합니다.  
  
         \-또는\-  
  
    -   **속성** 창을 사용하여 XSLT 스타일시트를 추가합니다.문서 **속성 창**에서 **스타일시트** 필드의 **찾아보기** 단추를 클릭하고 XSLT 스타일시트를 선택한 다음 **열기**를 클릭합니다.  
  
3.  **XML 편집기** 도구 모음에서 **XSL 출력표시** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  XML 문서에 연결된 스타일시트가 없을 경우 대화 상자에서 사용할 스타일시트를 지정하라는 메시지가 나타납니다.  
    >   
    >  XSLT 변환의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.  
  
### XSLT 스타일시트에서 XSLT 변환을 실행하려면  
  
1.  XML 편집기에서 XSLT 스타일시트를 엽니다.  
  
2.  문서 **속성** 창의 **입력** 필드에서 XML 문서를 지정합니다.  
  
    > [!NOTE]
    >  XML 문서는 변환에 사용되는 입력 문서입니다.XSLT 변환을 시작할 때 문서가 지정되어 있지 않으면 **파일 열기** 대화 상자가 나타납니다. 그러면 이 대화 상자에서 문서를 지정할 수 있습니다.  
  
3.  **XML 편집기** 도구 모음에서 **XSLT 출력표시** 단추를 클릭합니다.  
  
     XSLT 변환의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.  
  
### 다른 출력 파일 이름을 지정하려면  
  
1.  문서 **속성** 창의 **출력** 필드에서 파일 이름을 지정합니다.  
  
2.  **XML 편집기** 도구 모음에서 **XSLT 출력표시** 단추를 클릭합니다.  
  
     XSLT 변환 결과로 생성된 출력이 새 문서 창에 표시되며 출력 창에서 사용되는 편집기는 **Output** 문서 속성의 파일 확장명에 따라 달라집니다.  
  
## 참고 항목  
 [XML 편집기](../xml-tools/xml-editor.md)