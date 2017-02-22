---
title: "XDCMake Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.task.xdcmake"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "XDCMake task (MSBuild (Visual C++))"
  - "MSBuild (Visual C++), XDCMake task"
ms.assetid: a7de9c64-903a-4a02-85f3-f37672270f25
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# XDCMake Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

XML 문서 주석 파일\(.xdc\)을 .xml 파일에 병합하는 XML 문서 도구\(xdcmake.exe\)를 래핑합니다.  
  
 .xdc 파일은 Visual C\+\+ 소스 코드와 컴파일에서 [\/doc](/visual-cpp/build/reference/doc-process-documentation-comments-c-cpp) 컴파일러 옵션을 사용하여 설명서 주석을 제공할 때 만들어집니다.  자세한 내용은 xdcmake.exe에 대한 [XDCMake 참조](/visual-cpp/ide/xdcmake-reference), [XML 문서 생성기 도구 속성 페이지](/visual-cpp/ide/xml-document-generator-tool-property-pages) 및 명령줄 도움말 옵션\(**\/?**\)을 참조하십시오.  
  
## 설명  
 기본적으로 xdcmake.exe 도구는 몇 가지 명령줄 옵션을 지원합니다.  **\/old** 명령줄 옵션을 지정할 때 추가 옵션이 지원됩니다.  
  
## 매개 변수  
 다음 표에서는 **XDCMake** 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**AdditionalDocumentFile**|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 병합할 추가 .xdc 파일을 하나 이상 지정합니다.<br /><br /> 자세한 내용은 [XML 문서 생성기 도구 속성 페이지](/visual-cpp/ide/xml-document-generator-tool-property-pages)의 **추가 문서 파일** 설명을 참조하십시오.  또한 xdcmake.exe에 대한 **\/old** 및 **\/Fs** 명령줄 옵션을 참조하십시오.|  
|**AdditionalOptions**|선택적 **String** 매개 변수입니다.<br /><br /> 명령줄에 지정된 것처럼 옵션 목록입니다.  예를 들어, "*\/option1 \/option2 \/option\#*"입니다.  이 매개 변수를 사용하여 다른 **XDCMake** 작업 매개 변수로 표현되지 않는 옵션을 지정합니다.<br /><br /> 자세한 내용은 xdcmake.exe에 대한 [XDCMake 참조](/visual-cpp/ide/xdcmake-reference), [XML 문서 생성기 도구 속성 페이지](/visual-cpp/ide/xml-document-generator-tool-property-pages) 및 명령줄 도움말\(**\/?**\)을 참조하십시오.|  
|**DocumentLibraryDependencies**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true` 및 현재 프로젝트가 솔루션의 정적 라이브러리\(.lib\) 프로젝트에 종속적인 경우 해당 라이브러리 프로젝트의 .xdc 파일은 현재 프로젝트에 대한 .xml 파일 출력에 포함됩니다.<br /><br /> 자세한 내용은 [XML 문서 생성기 도구 속성 페이지](/visual-cpp/ide/xml-document-generator-tool-property-pages)의 **라이브러리 종속성 문서화** 설명을 참조하십시오.|  
|**OutputFile**|선택적 **String** 매개 변수입니다.<br /><br /> 기본 출력 파일 이름을 재정의합니다.  기본 이름은 처리되는 첫 번째 .xdc 파일의 이름에서 파생됩니다.<br /><br /> 자세한 내용은 [XDCMake 참조](/visual-cpp/ide/xdcmake-reference)의 **\/out:**`filename` 옵션을 참조하십시오.  또한 xdcmake.exe에 대한 **\/old** 및 **\/Fo** 명령줄 옵션을 참조하십시오.|  
|**ProjectName**|선택적 **String** 매개 변수입니다.<br /><br /> 현재 프로젝트의 이름입니다.|  
|**SlashOld**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 추가 xdcmake.exe 옵션을 활성화합니다.<br /><br /> 자세한 내용은 xdcmake.exe에 대한 **\/old** 명령줄 옵션을 참조하십시오.|  
|**Sources**|필수적 `ITaskItem[]` 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 소스 파일 항목의 배열을 정의합니다.|  
|**SuppressStartupBanner**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 작업을 시작할 때 저작권과 버전 번호 메시지가 표시되지 않도록 합니다.<br /><br /> 자세한 내용은 [XDCMake 참조](/visual-cpp/ide/xdcmake-reference)의 **\/nologo** 옵션을 참조하십시오.|  
|**TrackerLogDirectory**|선택적 **String** 매개 변수입니다.<br /><br /> 추적기 로그용 디렉터리를 지정합니다.|  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)