---
title: 명령줄 스위치를 추가 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- command-line switches, adding
- command-line switches, retrieving
- IVsAppCommandLine::GetOption method
- command line, switches
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: daef07d0b8dd02f6823717b0c0cb5d68d837ccde
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-command-line-switches"></a>명령줄 스위치를 추가합니다.
Devenv.exe를 실행할 때 VSPackage에 적용 되는 명령줄 스위치를 추가할 수 있습니다. 사용 하 여 <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> 스위치와 해당 속성의 이름을 선언 하 합니다. 이 예제에서는 myswitch 인 스위치 라는 VSPackage의 서브 클래스에 대 한 추가 됩니다 **AddCommandSwitchPackage** 인수 없이 및 자동으로 로드 하는 VSPackage를 사용 합니다.  
  
```csharp  
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]  
```  
  
 명명 된 매개 변수는 다음 표에 나와 있습니다.  
  
 인수  
 스위치에 대 한 인수의 수입니다. 일 수 있습니다 "*", 또는 인수 목록입니다.  
  
 DemandLoad  
 그렇지 않으면 0으로 설정 하는 1로 설정 하면 자동으로 VSPackage를 로드 합니다.  
  
 HelpString  
 도움말 문자열 또는 리소스 ID 문자열의 사용을 표시 하려면 **devenv /?**합니다.  
  
 이름  
 스위치입니다.  
  
 PackageGuid  
 패키지의 GUID입니다.  
  
 인수의 첫 번째 값은 일반적으로 0 또는 1입니다. 특수 한 값인 ' *' 명령줄의 전체 나머지 인수 임을 나타내기 위해 사용할 수 있습니다. 이 디버깅 여기서 사용자 디버거 명령 문자열을 전달 해야 하는 시나리오에 유용할 수 있습니다.  
  
 DemandLoad 값은 `true` (1) 또는 `false` (0) VSPackage를 자동으로 로드할 수를 나타냅니다.  
  
 HelpString 값은 고 devenv에 표시 되는 문자열의 리소스 ID /? 도움말 표시 합니다. 이 값은 "#nnn" nnn은 정수 형식에서 이어야 합니다. 리소스 파일에 문자열 값은 새 줄 문자로 종료 해야 합니다.  
  
 이름 값은 스위치의 이름입니다.  
  
 PackageGuid 값은이 스위치를 구현 하는 패키지의 GUID입니다. IDE는이 GUID를 사용 하 여 명령줄 스위치 적용 되는 레지스트리에서 VSPackage를 찾습니다.  
  
## <a name="retrieving-command-line-switches"></a>명령줄 스위치를 검색합니다.  
 패키지를 로드할 때 다음 단계를 완료 하 여 명령줄 스위치를 검색할 수 있습니다.  
  
1.  VSPackage의에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현, 호출 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> 가져오려는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> 인터페이스입니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> 를 사용자가 입력 한 명령줄 스위치를 검색 합니다.  
  
 다음 코드 myswitch 인 명령줄 스위치는 사용자가 입력 한 있는지 여부를 확인 하는 방법을 보여 줍니다.  
  
```csharp  
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine));  
  
int isPresent = 0;  
string optionValue = "";  
  
cmdline.GetOption("MySwitch", out isPresent, out optionValue);  
```  
  
 패키지를 로드할 때마다 명령줄 스위치에 대 한 확인 작업은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)   
 [CreatePkgDef 유틸리티](../extensibility/internals/createpkgdef-utility.md)   
 [. Pkgdef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)