---
title: VSIX 패키지 서명 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84166ed96fb49567f4ede3e8e0c4b7e8ba3cc814
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="signing-vsix-packages"></a>VSIX 패키지 서명
확장 프로그램 어셈블리는 Visual Studio에서 실행할 수 있지만 이렇게 하는 것이 좋습니다 전에 서명할 필요가 없습니다.  
  
 보안 확장 프로그램을 설정 하 고 있는지와 조작 되지 않았는지 확인 하려면 VSIX 패키지에 디지털 서명을 추가할 수 있습니다. VSIX는 서명 되며, VSIX 설치 관리자는 서명 및 서명 자체에 대 한 자세한 정보를 나타내는 메시지가 표시 됩니다. VSIX의 내용이 수정 되었으면, VSIX 다시 서명 되지 않은 경우 VSIX 설치 관리자 서명이 유효 하지 않으면 표시 됩니다. 설치가 중지 되지 않으면 하지만 사용자에 게 경고가 표시 됩니다.  
  
> [!IMPORTANT]
>  2015 년 부터는 이외의 노드에 SHA256 암호화를 사용 하 여 서명 되는 VSIX 패키지에 잘못 된 서명이 있는 것으로 식별 됩니다. VSIX 설치가 차단 되지 않습니다 되지만 사용자는 경고가 표시 됩니다.  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>한 VSIX VSIXSignTool와 서명  
 서명 도구에서 사용할 수 있는 SHA256 암호화는 [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) 에서 nuget.org에 [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool)합니다.  
  
#### <a name="to-use-the-vsixsigntool"></a>VSIXSignTool 사용 하려면  
  
1.  프로그램 VSIX 프로젝트에 추가 합니다.  
  
2.  솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭을 선택 하면 **추가 &#124; NuGet 패키지 관리**합니다.  NuGet 및 NuGet 패키지 참조 추가 대 한 자세한 내용은 참조는 [NuGet 설명서](/NuGet) 및 [패키지 관리자 UI](/NuGet/Tools/Package-Manager-UI) 항목입니다.  
  
3.  VSIXSignTool VisualStudioExtensibility에서 검색 하 고 NuGet 패키지를 설치 합니다.  
  
4.  이제 프로젝트의 로컬 패키지 위치에서의 VSIXSignTool를 실행할 수 있습니다. 시나리오에 맞는 서명 도구의 명령줄 도움말을 참조 하십시오. (VSIXSignTool.exe /?).  
  
 예를 들어 암호로 보호 된 인증서 파일에 서명 합니다.  
  
 VSIXSignTool.exe 기호 /f \<certfile > /p \<암호 > \<VSIXfile >  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 확장 전달](../extensibility/shipping-visual-studio-extensions.md)