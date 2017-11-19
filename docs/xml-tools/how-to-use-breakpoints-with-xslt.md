---
title: "방법: XSLT에 중단점 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8c077cab7bf02023d0bfb1714940f98020600477
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-breakpoints-with-xslt"></a>방법: XSLT에 중단점 사용
XSLT 스타일시트 또는 XML 소스 문서에서 중단점을 설정할 수 있습니다. 태그에 중단점을 설정한 경우 실행을 시작하면 소스 줄 정보가 있는 다음 문으로 중단점이 이동합니다.  
  
 자세한 내용은 참조 [디버깅 기본 사항: 중단점](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)합니다.  
  
## <a name="set-a-breakpoint-in-a-style-sheet"></a>스타일시트에서 중단점 설정  
 중단점은 XSLT 스타일시트의 모든 시작 태그, 끝 태그 및 텍스트 노드에 설정할 수 있으며 스크립트 블록의 코드에 대해서도 설정할 수 있습니다.  
  
#### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>스타일시트에서 중단점을 설정하려면  
  
1.  XML 편집기에서 스타일시트를 엽니다.  
  
2.  중단점 위치에 커서의 위치를 마우스 오른쪽 단추로 가리킨 **중단점**를 클릭 하 고 **중단점 삽입**합니다.  
  
3.  찾아보기 단추를 클릭 (**...** )에 **입력** 문서 속성 창의 필드입니다.  
  
4.  XML 원본 문서를 찾아서 클릭 하 여 **열려**합니다.  
  
     그러면 XSLT 변형에 사용되는 소스 문서 파일이 설정됩니다.  
  
5.  클릭는 **XSL 디버깅** XML 편집기 도구 모음 단추입니다.  
  
## <a name="set-a-breakpoint-in-an-xml-source-document"></a>XML 소스 문서에서 중단점 설정  
 또한 중단점은 XML 소스 문서의 요소, 특성, 네임스페이스 노드, 주석, 처리 명령 및 텍스트 노드에 대해 설정할 수 있습니다. 그러나 부모 요소에서 상속되는 네임스페이스 노드나 문서 노드에 대해서는 중단점을 설정할 수 없습니다.  
  
#### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>XML 소스 문서에서 중단점을 설정하려면  
  
1.  XML 편집기에서 XML 문서를 엽니다.  
  
2.  중단점 위치에 커서의 위치를 마우스 오른쪽 단추로 가리킨 **중단점**를 클릭 하 고 **중단점 삽입**합니다.  
  
3.  찾아보기 단추를 클릭 (**...** )에 **스타일 시트** 문서 속성 창의 필드입니다.  
  
4.  XML 원본 문서를 찾아서 클릭 하 여 **열려**합니다.  
  
     그러면 XSLT 변형에 사용되는 소스 문서 파일이 설정됩니다.  
  
5.  클릭는 **XSL 디버깅** XML 편집기 도구 모음 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: XSLT 스타일시트 디버그](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)