---
title: "Unable to read the resource information from the licx file | Microsoft Docs"
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
  - "vs.tasklisterror.fail_reading_licx_file"
ms.assetid: e59f0965-fa1c-4852-bd39-63430d5b7d9f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Unable to read the resource information from the licx file
프로젝트 시스템에서 .licx 파일을 읽을 수 없습니다.  라이센스 준비의 일부로 프로젝트 시스템에서는 텍스트 .licx 파일을 COM\+ 라이센스 모델과 사용하기에 적합한 이진 리소스 파일로 변환합니다.  
  
 .licx 파일은 폼에 라이센스가 있는 컨트롤을 추가할 때마다 Windows Forms 디자이너가 자동으로 생성하고 업데이트합니다.  프로젝트마다 .licx 파일이 하나씩 있으며 루트 폴더에 있습니다. 이 파일의 이름은 항상 Licenses.licx입니다.  
  
 이 오류가 발생하는 몇 가지 이유는 다음과 같습니다.  
  
-   사용 권한이 거부되었습니다.  
  
-   웹 프로젝트가 있는 웹 서버와의 통신이 끊겼습니다.  
  
 이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
## 참고 항목  
 [방법: 구성 요소 및 컨트롤 라이센스](../Topic/How%20to:%20License%20Components%20and%20Controls.md)