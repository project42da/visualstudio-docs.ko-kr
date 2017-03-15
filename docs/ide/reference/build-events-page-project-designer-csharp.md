---
title: "프로젝트 디자이너, 빌드 이벤트 페이지(C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.ProjectPropertiesBuildEvents"
helpviewer_keywords: 
  - "빌드 이벤트"
  - "프로젝트 디자이너, 빌드 이벤트 페이지"
  - "빌드 전 이벤트"
  - "빌드 후 이벤트"
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 프로젝트 디자이너, 빌드 이벤트 페이지(C#)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**프로젝트 디자이너**의 **빌드 이벤트** 페이지를 사용하여 빌드 구성 지침을 지정할 수 있습니다.  또한 빌드 후 이벤트가 실행되는 조건을 지정할 수도 있습니다.  자세한 내용은 [방법: 빌드 이벤트 지정\(C\#\)](../../ide/how-to-specify-build-events-csharp.md) 및 [방법: 빌드 이벤트 지정\(Visual Basic\)](../../ide/how-to-specify-build-events-visual-basic.md)를 참조하십시오.  
  
## UI 요소 목록  
 **구성**  
 이 컨트롤은 이 페이지에서 편집할 수 없습니다.  이 컨트롤에 대한 설명은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](../../ide/reference/build-page-project-designer-csharp.md)를 참조하십시오.  
  
 **플랫폼**  
 이 컨트롤은 이 페이지에서 편집할 수 없습니다.  이 컨트롤에 대한 설명은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](../../ide/reference/build-page-project-designer-csharp.md)를 참조하십시오.  
  
 **빌드 전 이벤트 명령줄**  
 빌드를 시작하기 전에 실행할 명령을 지정합니다.  긴 명령을 입력하려면 **빌드 전 편집**을 클릭하여 [빌드 전 이벤트\/빌드 후 이벤트 명령줄 대화 상자](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)를 표시합니다.  
  
> [!NOTE]
>  빌드 전 이벤트는 프로젝트가 최신 상태이고 빌드가 트리거되지 않은 경우 실행되지 않습니다.  
  
 **빌드 후 이벤트 명령줄**  
 빌드가 끝난 후 실행할 명령을 지정합니다.  긴 명령을 입력하려면 **빌드 후 편집**을 클릭하여 **빌드 전 이벤트\/빌드 후 이벤트 명령줄 대화 상자**를 표시합니다.  
  
> [!NOTE]
>  .bat 파일을 실행하는 모든 빌드 후 명령 앞에 `call` 문을 추가하십시오.  예를 들면 `call C:\MyFile.bat` 또는 `call C:\MyFile.bat call C:\MyFile2.bat`를 사용할 수 있습니다.  
  
 **빌드 후 이벤트 실행**  
 다음 표에서와 같이 빌드 후 이벤트를 실행하는 조건을 지정합니다.  
  
|옵션|결과|  
|--------|--------|  
|**항상**|빌드 성공 여부에 상관없이 항상 빌드 후 이벤트를 실행합니다.|  
|**빌드가 성공한 경우**|빌드가 성공하면 빌드 후 이벤트를 실행합니다.  따라서 빌드가 성공하면 최신 프로젝트에 대해서도 빌드 후 이벤트가 실행됩니다.|  
|**빌드에서 프로젝트 출력을 업데이트한 경우**|컴파일러의 출력 파일\(.exe 또는 .dll\)이 이전 컴파일러 출력 파일과 다른 경우에만 빌드 후 이벤트가 실행됩니다.  따라서 최신 프로젝트일 경우에는 빌드 후 이벤트가 실행되지 않습니다.|  
  
## 참고 항목  
 [방법: 빌드 이벤트 지정\(Visual Basic\)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [방법: 빌드 이벤트 지정\(C\#\)](../../ide/how-to-specify-build-events-csharp.md)   
 [프로젝트 속성 참조](../../ide/reference/project-properties-reference.md)   
 [Visual Studio에서 응용 프로그램　빌드](../../ide/compiling-and-building-in-visual-studio.md)