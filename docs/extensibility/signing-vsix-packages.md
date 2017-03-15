---
title: "VSIX 패키지 서명 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시그니처(signature)"
  - "서명"
  - "authenticode"
  - "vsix"
  - "패키지"
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# VSIX 패키지 서명
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

확장 프로그램 어셈블리는 Visual Studio에서 실행 하기 전에 작업을 수행 하는 것이 좋습니다 서명할 필요가 없습니다.  
  
 확장 프로그램을 보호 하 고 변조 되지 않았는지 확인 하려는 경우에 VSIX 패키지에 디지털 서명을 추가할 수 있습니다. VSIX 서명 하는 경우 VSIX 설치 관리자는 서명 및 서명 자체에 대 한 자세한 내용은 되었다는 메시지가 표시 됩니다. VSIX의 내용을 수정 된 경우 VSIX 다시 서명 되지 않았다는 VSIX 설치 관리자 서명이 유효 하지 않으면 표시 됩니다. 설치가 중지 되지 않으면 하지만 사용자에 게 경고가 표시 됩니다.  
  
> [!IMPORTANT]
>  2015 년 부터는 이외의 SHA256 암호화를 사용 하 여 서명 VSIX 패키지에 잘못 된 서명이 있는 것으로 식별 됩니다. VSIX 설치가 차단 되지 않습니다 하지만 사용자를 열라는 경고가 표시 됩니다.  
  
## VSIXSignTool와 VSIX 서명  
 서명 도구에서 사용할 수는 s h a 256 암호화는 [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) 에서 nuget.org에서 [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool)합니다.  
  
#### VSIXSignTool를 사용 하 여  
  
1.  프로그램 VSIX 프로젝트에 추가 합니다.  
  
2.  를 선택 하는 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 **추가 &#124; NuGet 패키지 관리**합니다.  NuGet 및 NuGet 추가 대 한 자세한 내용은 패키지 참조 [NuGet 개요](http://docs.nuget.org/) 및 [관리 NuGet 패키지를 사용 하 여 대화 상자](http://docs.nuget.org/Consume/Package-Manager-Dialog)합니다.  
  
3.  VSIXSignTool VisualStudioExtensibility에서 검색 하 고 NuGet 패키지를 설치 합니다.  
  
4.  이제 프로젝트의 로컬 패키지 위치에서의 VSIXSignTool를 실행할 수 있습니다. 서명 시나리오에는 도구의 명령줄 도움말을 참조 하십시오 \(VSIXSignTool.exe \/?\).  
  
 예를 들어 암호 보호 된 인증서 파일을 서명 합니다.  
  
 VSIXSignTool.exe 기호 \/f \< certfile \>\/p \< 암호 \>\< VSIXfile \>  
  
## 참고 항목  
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)