---
title: "Could not instantiate the licenses processor | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.no_licx_generator"
ms.assetid: 9e95d590-f41f-4cfa-bc73-fadeacfdb879
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Could not instantiate the licenses processor
.licx 파일을 이진 리소스로 변환하는 데 사용한 도구를 인스턴스화할 수 없습니다.  
  
 컴파일의 일부로 프로젝트 시스템에서는 텍스트 .licx 파일을 .NET 컨트롤 라이센스를 지원하는 이진 리소스로 변환합니다.  그러면 이진 리소스가 프로젝트 출력에 포함됩니다.  
  
 이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
 .licx 파일은 폼에 라이센스가 있는 컨트롤을 추가할 때마다 Windows Forms 디자이너가 자동으로 생성하고 업데이트합니다.  프로젝트마다 .licx 파일이 하나씩 있으며 루트 폴더에 있습니다. 이 파일의 이름은 항상 Licenses.licx입니다.  
  
 **이 오류를 해결하려면**  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 설치합니다.  
  
## 참고 항목  
 [방법: 구성 요소 및 컨트롤 라이센스](../Topic/How%20to:%20License%20Components%20and%20Controls.md)