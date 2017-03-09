---
title: "다음 프로젝트 구성이 변경되었습니다. &lt;구성&gt;. 빌드하시겠습니까? | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.Message.BuildOutOfDateProjects"
ms.assetid: d0711f3b-3a2e-4247-afad-9e6468f9df96
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 다음 프로젝트 구성이 변경되었습니다. &lt;구성&gt;. 빌드하시겠습니까?
Visual Studio 프로젝트를 편집하고 있거나 솔루션 탐색기에서 프로젝트를 선택했으며, 프로젝트를 시작\(F5\)하도록 선택했거나 디버깅하지 않고 시작\(Ctrl\+F5\)하도록 선택했습니다. 프로젝트가 마지막 빌드 이후 수정되었더라도, 하나 이상의 프로젝트에서는 다시 빌드를 사용하지 않고 디버깅을 수행할 수 있습니다.  
  
 IDE\(통합 개발 환경\)에서는 다시 빌드하지 않고 디버깅을 수행할 수 있는 프로젝트 다시 빌드의 사용 여부를 묻습니다.  
  
### 이 메시지에 응답하려면  
  
-   메시지 하단에서 단추 중 하나를 선택합니다. 옵션은 다음과 같습니다.  
  
|용어|정의|  
|--------|--------|  
|**예**|이전 프로젝트를 다시 빌드합니다. 즉,<br /><br /> -   프로젝트가 아직 빌드되지 않았다면 프로젝트가 빌드됩니다.<br />-   마지막 빌드 이후 프로젝트가 수정되었다면 프로젝트가 다시 빌드됩니다.<br />-   프로젝트가 디버깅되거나 또는 디버깅 없이 프로젝트가 시작됩니다.|  
|**아니요**|디버깅하기 전에, 다시 빌드해야 하는 이전 프로젝트만 다시 빌드합니다. 즉,<br /><br /> -   프로젝트에서 다시 빌드하지 않고 디버깅을 수행할 수 있다면 프로젝트가 다시 빌드되지 않습니다\(예: Visual C\+\+ MFC 응용 프로그램 프로젝트\).<br />-   프로젝트에서 디버깅하기 전에 다시 빌드해야 할 경우 프로젝트가 다시 빌드됩니다\(예: Visual Basic 프로젝트\).<br />-   프로젝트가 디버깅되거나 또는 디버깅 없이 프로젝트가 시작됩니다.|  
|**취소**|현재 작업이 중지됩니다. 프로젝트가 빌드되거나, 시작되거나, 디버깅되지 않습니다.|  
  
## 참고 항목  
 [구성 관리자 대화 상자](http://msdn.microsoft.com/ko-kr/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [How to: Create Solution and Project Build Configurations](../Topic/How%20to:%20Create%20Solution%20and%20Project%20Build%20Configurations.md)   
 [방법: 프로젝트 종속성 만들기 및 제거](../ide/how-to-create-and-remove-project-dependencies.md)   
 [Project Dependencies Dialog Box](http://msdn.microsoft.com/ko-kr/d66e48c3-3722-40dd-99b4-53d93cac128e)   
 [Project Dependencies, Common Properties, Solution Property Pages Dialog Box](http://msdn.microsoft.com/ko-kr/2ba638fc-719c-4a79-b166-3455a4374e31)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)   
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [NIB: 컨테이너로서의 프로젝트](http://msdn.microsoft.com/ko-kr/87d40f63-f487-4767-8963-64beec27ba1b)   
 [NIB: 프로젝트의 항목 관리](http://msdn.microsoft.com/ko-kr/762e606b-7f44-4b66-97a1-e30a703654a0)