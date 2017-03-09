---
title: "Could not transform licenses file &#39;file&#39; into a binary resource. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.licx_generator_failed"
ms.assetid: 875e948c-d7a3-4ffc-be0d-f341de5f6310
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Could not transform licenses file &#39;file&#39; into a binary resource. &lt;reason&gt;
.licx 파일을 이진 리소스로 변환하는 데 사용한 라이센스 처리기에 몇 가지 이유로 오류가 발생했습니다.  
  
 이 오류는 일반적으로 잘못된 .licx 파일로 인해 발생합니다.  예를 들어, 텍스트 편집기에서 파일을 열고 수정한 경우가 이에 해당합니다.  
  
 이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
### 이 오류를 해결하려면  
  
1.  솔루션 탐색기에서 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.  
  
3.  솔루션 탐색기에서 obj 폴더를 확장한 다음 **디버그** 폴더를 확장합니다.  
  
4.  "myApplication.exe.licenses"라는 파일을 찾습니다. 여기서 myApplication은 Windows Forms 응용 프로그램의 이름입니다.  
  
5.  이 파일을 삭제하고 솔루션을 다시 빌드합니다.  
  
## 참고 항목  
 [방법: 구성 요소 및 컨트롤 라이센스](../Topic/How%20to:%20License%20Components%20and%20Controls.md)