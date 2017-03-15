---
title: "RC Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions"
  - "vc.task.rc"
  - "VC.Project.VCResourceCompilerTool.SuppressStartupBanner"
  - "VC.Project.VCResourceCompilerTool.NullTerminateStrings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "RC task (MSBuild (Visual C++))"
  - "MSBuild (Visual C++), RC task"
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# RC Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Microsoft Windows Resource Compiler 도구인 rc.exe를 래핑합니다.  **RC** 작업은 커서, 아이콘, 비트맵, 대화 상자 및 글꼴 같은 리소스를 리소스\(.res\) 파일로 컴파일입니다.  자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Resource Compiler"를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 RC 작업의 매개 변수에 대해 설명합니다.  대부분의 작업 매개 변수 및 일부 매개 변수 집합은 명령줄 옵션에 해당합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**AdditionalIncludeDirectories**|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 포함 파일을 찾기 위해 검색할 디렉터리 목록에 디렉터리를 추가합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/I** 옵션을 참조하십시오.|  
|**AdditionalOptions**|선택적 **String** 매개 변수입니다.<br /><br /> 명령줄 옵션 목록 또는 예를 들어, **"***\/option1 \/option2 \/option\#*"입니다.  이 매개 변수를 사용하여 다른 **RC** 작업 매개 변수로 표현되지 않는 명령줄 옵션을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 옵션을 참조하십시오.|  
|**Culture**|선택적 **String** 매개 변수입니다.<br /><br /> 리소스에 사용되는 문화권을 나타내는 로캘 ID를 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/l** 옵션을 참조하십시오.|  
|**IgnoreStandardIncludePath**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 헤더 파일이나 리소스 파일을 검색할 때 리소스 컴파일러가 INCLUDE 환경 변수를 확인하는 것이 방지됩니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/x** 옵션을 참조하십시오.|  
|**NullTerminateStrings**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 문자열 테이블에서 모든 문자열을 null 종료합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/n** 옵션을 참조하십시오.|  
|**PreprocessorDefinitions**|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 리소스 컴파일러에 대해 전처리기 기호를 하나 이상 정의합니다.  매크로 기호 목록을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/d** 옵션을 참조하십시오.  또한 이 테이블의 **UndefinePreprocessorDefinitions**를 참조하십시오.|  
|**ResourceOutputFileName**|선택적 **String** 매개 변수입니다.<br /><br /> 리소스 파일의 이름을 지정합니다.  리소스 파일 이름을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/fo** 옵션을 참조하십시오.|  
|**ShowProgress**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 컴파일러의 프로세스에 대해 보고하는 메시지를 표시합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/v** 옵션을 참조하십시오.|  
|**Source**|필수적 `ITaskItem[]` 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 소스 파일 항목의 배열을 정의합니다.|  
|**SuppressStartupBanner**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 작업을 시작할 때 저작권과 버전 번호 메시지가 표시되지 않도록 합니다.<br /><br /> 자세한 내용은 **\/?** 명령줄 옵션을 입력한 다음 **\/nologo** 옵션을 참조하십시오.|  
|**TrackerLogDirectory**|선택적 **String** 매개 변수입니다.<br /><br /> 추적기 로그 디렉터리를 지정합니다.|  
|**UndefinePreprocessorDefinitions**|전처리기 기호 정의를 해제합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트에서 [Using RC \(The RC Command Line\)](http://go.microsoft.com/fwlink/?LinkId=155730)의 **\/u** 옵션을 참조하십시오.  또한 이 테이블의 **PreprocessorDefinitions**를 참조하십시오.|  
  
## 설명  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)