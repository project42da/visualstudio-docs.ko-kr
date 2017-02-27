---
title: "명령줄 스위치를 추가합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "추가 명령줄 스위치"
  - "명령줄 스위치, 검색"
  - "IVsAppCommandLine::GetOption 메서드"
  - "명령줄 스위치"
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 명령줄 스위치를 추가합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Devenv.exe를 실행할 때 VSPackage에 적용 되는 명령줄 스위치를 추가할 수 있습니다. 사용 하 여 <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> 스위치와 해당 속성의 이름을 선언할 수 있습니다. 이 예제는 myswitch 인 스위치 추가 하는 라는 VSPackage의 서브 클래스에 대 한 **AddCommandSwitchPackage** 인수 없이 VSPackage를 자동으로 로드 합니다.  
  
```c#  
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]  
```  
  
 명명 된 매개 변수는 다음 표에 나와 있습니다.  
  
 인수  
 스위치에 대 한 인수의 수입니다. 일 수 있습니다 "\*", 또는 인수 목록입니다.  
  
 DemandLoad  
 그렇지 않으면 0으로 설정 하는 1로 설정 하면 VSPackage를 자동으로 로드 합니다.  
  
 HelpString  
 도움말 문자열 또는 리소스 ID 문자열의 사용을 표시 하려면 **devenv \/?**합니다.  
  
 이름  
 스위치입니다.  
  
 PackageGuid  
 패키지의 GUID입니다.  
  
 인수의 첫 번째 값은 일반적으로 0 또는 1입니다. 특수 값 ' \*' 명령줄의 전체 나머지 인수 임을 나타내는 데 사용할 수 있습니다. 이 디버깅 여기서 사용자 디버거 명령 문자열을 전달 해야 하는 시나리오에 유용할 수 있습니다.  
  
 DemandLoad 값은 `true` \(1\) 또는 `false` \(0\) VSPackage를 자동으로 로드할 수를 나타냅니다.  
  
 HelpString 값은 리소스 ID는 devenv에 표시 되는 문자열의 \/? 도움말 표시 합니다. 이 값은 "\#nnn" 여기서 nnn은 정수 형식에서 이어야 합니다. 리소스 파일에 문자열 값은 줄 바꿈 문자에서 끝나야 합니다.  
  
 이름 값은 스위치의 이름입니다.  
  
 PackageGuid 값은이 스위치를 구현 하는 패키지의 GUID입니다. IDE는이 GUID를 사용 하 여 명령줄 스위치 적용 되는 레지스트리에서 VSPackage를 찾습니다.  
  
## 명령줄 스위치를 검색합니다.  
 패키지 로드 되 면 다음 단계를 완료 하 여 명령줄 스위치를 검색할 수 있습니다.  
  
1.  VSPackage의에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현, 호출 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> 가져오려는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> 인터페이스입니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> 사용자가 입력 한 명령줄 스위치를 검색할 수 있습니다.  
  
 다음 코드는 myswitch 인 명령줄 스위치는 사용자가 입력 한 있는지 여부를 확인 하는 방법을 보여 줍니다.  
  
```c#  
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine)); int isPresent = 0; string optionValue = ""; cmdline.GetOption("MySwitch", out isPresent, out optionValue);  
```  
  
 패키지를 로드할 때마다 명령줄 스위치에 대 한 확인 작업은  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)   
 [CreatePkgDef 유틸리티](../extensibility/internals/createpkgdef-utility.md)   
 [. Pkgdef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)