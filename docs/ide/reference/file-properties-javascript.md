---
title: "파일 속성, JavaScript | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "javascript.project.property.expandedsdknode.fileversion"
  - "javascript.project.property.expandedsdknode.uri"
  - "javascript.project.property.expandedsdknode.filename"
  - "javascript.project.property.reference.description"
  - "javascript.project.property.reference.specificversion"
  - "javascript.project.property.reference.identity"
  - "javascript.project.property.fullpath"
  - "javascript.project.property.packageaction"
  - "javascript.project.property.reference.package"
  - "javascript.project.property.copytooutputdirectory"
  - "javascript.project.property.expandedsdknode.sdkpath"
  - "javascript.project.property.reference.filetype"
  - "javascript.project.property.reference.culture"
  - "javascript.project.property.filename"
  - "javascript.project.property.reference.resolvedpath"
  - "javascript.project.property.reference.version"
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 파일 속성, JavaScript
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

파일의 속성을 사용하여 프로젝트 시스템에서 파일에 대해 수행할 동작을 지정할 수 있습니다.  예를 들어, 파일을 리소스 파일로 패키지를 추가할지 여부를 나타내는 파일 속성을 설정할 수 있습니다.  
  
 솔루션 탐색기에서 파일을 선택한 다음 속성 창에서 속성을 검사할 수 있습니다.  JavaScript 파일이 있는 네 가지 속성:  **출력 디렉터리로 복사**,  **패키지 작업**,  **파일 이름이**, 및  **파일 경로**.  
  
## 파일 속성  
 이 섹션에서는 JavaScript 파일에 공통 된 속성을 설명합니다.  
  
### 출력 디렉터리로 복사 속성  
 이 속성에서는 선택한 소스 파일을 출력 디렉터리로 복사할 조건을 지정합니다.  파일을 출력 디렉터리로 복사하지 않으려면 **복사 안 함**을 선택합니다.  그리고 파일을 항상 출력 디렉터리로 복사하려면 **항상 복사**를 선택합니다.  파일이 출력 디렉터리에 있는 이름이 같은 기존 파일보다 최신 버전인 경우에만 복사하려면 **변경된 내용만 복사**를 선택합니다.  
  
### 패키지 작업  
 **패키지 작업** 속성이 나타내는 빌드를 실행 하면 Visual Studio 파일에 수행할 작업입니다.  **패키지 작업** 몇 가지 값을 가질 수 있습니다.  
  
-   **없음** \-파일 패키지 매니페스트에 포함 되지 않습니다.  추가 정보 파일 같은 설명이 포함된 텍스트 파일을 예로 들 수 있습니다.  
  
-   **콘텐츠** \-패키지 매니페스트 파일이 포함 되어 있습니다.  예를 들어,이 설정은.htm,.js,.css, 이미지, 오디오 또는 비디오 파일에 대 한 기본값입니다.  
  
-   **매니페스트** – 파일 패키지 매니페스트에 포함 되지 않습니다.  대신, 패키지 매니페스트를 생성할 때 파일에 대 한 입력 사용 됩니다.  이 package.appxmanifest 파일에 대 한 기본값입니다.  
  
-   **자원** \-파일 패키지 매니페스트에 포함 되지 않습니다.  대신, 파일의 내용에는 패키지 리소스 인덱스 \(패키지 매니페스트로 이동 PRI\) 인덱싱됩니다.  일반적으로 리소스 파일에 사용됩니다.  
  
 기본값은  **패키지 작업** 를 솔루션에 추가 되는 파일의 확장명에 따라 다릅니다.  
  
### 파일 이름 속성  
 파일 이름에 읽기 전용 값으로 표시 됩니다.  파일 이름을 변경 하려면 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 하 고 선택 해야  **이름 바꾸기**.  
  
### 전체 경로 속성  
 전체 경로 파일에 읽기 전용 값으로 표시 됩니다.  파일의 경로 변경 하려면 솔루션 탐색기에서 파일 끌어서 놓기 및 할 수 있습니다.  
  
## 참조 파일 속성  
 설명 파일에서 참조 하는 공통 된 속성을 [!INCLUDE[win8_app_js](../../ide/reference/includes/win8_app_js_md.md)].  솔루션 탐색기에서.winmd 파일, SDK 참조, 프로젝트 간 참조를 또는 어셈블리 참조와 같은 참조를 선택 하면 다른 속성은 파일 형식에 따라 속성 창에 표시할 수 있습니다.  
  
### 문화권  
 참조와 연관 된 언어를 표시 합니다.  
  
### 파일 형식  
 참조의 파일 형식을 표시합니다.  
  
### 파일 버전  
 참조의 파일 버전을 표시합니다.  
  
### ID  
 프로젝트 파일에 저장 된 프로젝트에 사용 되는 참조의 id를 표시 합니다.  
  
### 패키지  
 패키지 매니페스트 참조와 연결 된 이름이 표시 됩니다.  
  
### 확인 된 경로  
 프로젝트에 사용 되는 참조 하는 경로 표시 합니다.  
  
### SDK 경로  
 경로가 참조 된 SDK 파일을 표시합니다.  
  
### Uri  
 파일을 원본 파일로 포함할 프로젝트의 HTML 이나 JavaScript 파일에 포함 해야 하는 URI를 표시 합니다.  
  
### 버전  
 참조의 버전을 표시합니다.  
  
## 참고 항목  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)