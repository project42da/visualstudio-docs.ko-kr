---
title: "찾기/명령 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.findcommandbox"
helpviewer_keywords: 
  - "찾기/명령 상자"
ms.assetid: c81736dd-7a26-4e11-95c8-c2a2e56d7a41
caps.latest.revision: 17
caps.handback.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 찾기/명령 상자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트를 검색 하는 Visual Studio 명령을 실행 하면  **찾기\/명령** 상자.  **찾기\/명령** 상자 toolbar 컨트롤을 계속 사용할 수 있지만 기본적으로 표시 되지 않는.  표시할 수는  **찾기\/명령** 상자를 선택 하 여  **단추 추가 \/ 제거** 에  **표준** 선택 하 고 도구 모음  **찾기**.  
  
 실행 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령, 큼 앞 보다 \(\>\) 기호.  
  
 **찾기\/명령** 입력란은 최근에 입력된 20개의 항목을 유지하며 이들 항목을 드롭다운 목록에 표시합니다.  화살표 키를 선택 하 여 목록을 탐색할 수 있습니다.  
  
 ![찾기&#47;명령 상자](../ide/media/findcommandbox.png "FindCommandBox")  
찾기\/명령 입력란  
  
## 텍스트 검색  
 텍스트를 지정 하는 경우 기본적으로는  **찾기\/명령** 상자을 입력 한 다음 선택 키를 Visual Studio 지정 된 옵션을 사용 하 여 현재 문서 또는 도구 창의 검색은  **파일에서 찾기** 대화 상자.  자세한 내용은 [텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)을 참조하십시오.  
  
## 명령 입력  
 사용 하는  **찾기\/명령** 상자 하나를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 또는 별칭 입력 텍스트를 검색 하는 대신의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령을 앞에 큰 보다 \(\>\) 기호.  예를 들면 다음과 같습니다.  
  
```  
>File.NewFile c:\temp\MyFile /t:"General\Text File"  
```  
  
 다른 방법으로, 명령 창을 사용하여 하나 또는 여러 명령을 입력하고 실행할 수 있습니다.  일부 명령이나 별칭은 독립적으로 입력하고 실행할 수 있지만 구문에 인수를 필요로 하는 명령이나 별칭도 있습니다.  인수가 있는 명령 목록을 보려면 [Visual Studio 명령](../ide/reference/visual-studio-commands.md)을 참조하십시오.  
  
## 이스케이프 문자  
 명령줄에 있는 캐럿\(^\) 문자는 캐럿 문자 바로 다음에 오는 문자가 제어 문자로 해석되는 대신 문자 그대로 해석됨을 의미합니다.  이 문자는 큰따옴표\("\), 공백, 선행 슬래시, 캐럿 등의 리터럴 문자를 매개 변수나 스위치 값에 포함시키는 데 사용할 수 있으며 스위치 이름은 예외입니다.  다음 예제를 참조하십시오.  
  
```  
>Edit.Find ^^t /regex  
```  
  
 캐럿은 따옴표의 내부 또는 외부에 있는지에 관계 없이 동일한 기능을 수행하며  줄의 마지막에 오는 캐럿 문자는 무시됩니다.  
  
## 참고 항목  
 [명령 창](../ide/reference/command-window.md)   
 [텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)