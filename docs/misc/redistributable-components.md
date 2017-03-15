---
title: "재배포 가능 구성 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "재배포 가능 구성 요소"
  - "설치[Visual Studio SDK], 재배포 가능 구성 요소"
ms.assetid: 5072281f-3cb3-4985-bd93-c7981233bf92
caps.latest.revision: 20
caps.handback.revision: 20
manager: "douge"
---
# 재배포 가능 구성 요소
[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 의 조건에 따라 사용자에 게 배포할 수 있는 코드가 포함 되어 있습니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK 라이센스 계약.  재배포 가능 구성 요소와 같은 Windows Installer 패키지 및 제품의 설치 프로세스의 일부로 병합 모듈이 사용자 Vspackages에 컴파일할 소스 코드를 포함 합니다.  
  
 다음 표에서 포함 된 재배포 가능 구성 요소는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK.  구성 요소에서 찾을 수 있습니다  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Redistributables\\.  
  
|파일 이름|설명|  
|-----------|--------|  
|VSSDKTestHost.exe|이 실행 파일은 설치의 일부로 설치할 수 있습니다.|  
  
## 재배포 가능 패키지를 설치합니다.  
 이러한 보안 취약점을 해결 또는 다른 중요 한 버그를 필요한 경우 Microsoft 업데이트를 제공할 수 있도록 실행 코드를 설치할 재배포 가능 구성 요소가 Windows Installer 패키지 \(.msi 파일\)로 제공 됩니다.  
  
 Windows Installer 하나의 패키지는 한 번에 설치할 수 있으므로 재배포 가능 패키지를 설치 순차적으로 여러 패키지를 설치 하는 별도 프로그램을 사용 해야 합니다.  이러한 프로그램을 자주 호출 됩니다 있는  *chainer* 또는  *부트스트래퍼*.  
  
> [!IMPORTANT]
>  *중첩 설치* \(도  *동시 설치*\) "중첩된" 제품을 독립적으로 패치할 수 없습니다 있기 때문에 Windows Installer에서 권장 되지 않습니다.  설치 제품에 패치가 가능 합니다.  때문에 [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)] 재배포 가능 패키지 파일 공유 디렉터리에 설치 하 고 독립 패치를 지원 해야 하 고 중첩 된 설치를 사용 하 여 설치 해야 합니다 없습니다.  
  
## 참고 항목  
 [제품 릴리스](../misc/releasing-a-visual-studio-integration-product.md)