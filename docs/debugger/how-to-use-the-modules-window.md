---
title: "방법: 모듈 창 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.modules"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 모듈 창"
  - "모듈 창"
  - "실행 파일, 디버깅 중에 표시"
  - "디버깅[Visual Studio], 모듈 표시"
  - "DLL, 디버깅 중에 표시"
  - "모듈, 표시"
ms.assetid: d840fdca-b035-4452-b652-72580c831896
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 모듈 창 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  SQL 또는 스크립트 디버깅에는 이 기능을 사용할 수 없습니다.  
  
 **모듈** 창에는 프로그램에 사용되는 DLL와 EXE가 나열되고 각각에 대한 관련 정보가 표시됩니다.  
  
### 중단 모드 또는 실행 모드에서 모듈 창을 표시하려면  
  
-   **디버그** 메뉴에서 **창**을 선택한 다음 **모듈**을 클릭합니다.  
  
     기본적으로 **모듈** 창에서는 모듈이 로드 순서대로 정렬됩니다.  그러나 열을 기준으로 정렬할 수도 있습니다.  
  
### 열별로 정렬하려면  
  
-   정렬 기준이 될 열 맨 위에 있는 단추를 클릭합니다.  
  
     바로 가기 메뉴를 사용하여 **모듈** 창에서 기호를 로드하거나 기호 경로를 지정할 수 있습니다.  
  
## 기호 로드  
 **모듈** 창에서 디버깅 기호가 로드된 모듈을 확인할 수 있습니다.  이 정보는 **기호 상태** 열에 표시됩니다.  상태가 **기호를 로드하지 않고 건너뛰었습니다.**, **PDB 파일을 찾거나 열 수 없습니다.** 또는 **포함\/제외 설정으로 로드가 비활성화되었습니다.**인 경우 디버깅 중인 컴퓨터의 기호 경로에서 기호를 로드하거나 Microsoft 공용 기호 서버에서 기호를 다운로드하도록 디버거에 지시할 수 있습니다.  자세한 내용은 [기호 파일\(.pdb\) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)을 참조하십시오.  
  
#### 기호를 수동으로 로드하려면  
  
1.  **모듈** 창에서 기호가 로드되지 않은 모듈을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  **다음에서 기호 로드**를 가리킨 다음 **Microsoft 공용 기호 서버** 또는 **기호 경로**를 클릭합니다.  
  
#### 기호 로드 설정을 변경하려면  
  
1.  **모듈** 창에서 모듈을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  **기호 설정**을 클릭합니다.  
  
     [기호 위치 및 로드 동작 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior)에 설명된 대로 이제 기호 로드 설정을 변경할 수 있습니다.  디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
#### 특정 모듈에 대한 기호 로드 동작을 변경하려면  
  
1.  **모듈** 창에서 모듈을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  **기호 로드 자동 설정**을 가리키고 **항상 수동으로 로드** 또는 **기본값**을 클릭합니다.  디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
## 참고 항목  
 [Breaking Execution](http://msdn.microsoft.com/ko-kr/30fc4643-f337-4651-b1ff-f2de2c098d40)   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [기호 파일\(.pdb\) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)