---
title: "방법: 서비스 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스, 등록"
ms.assetid: d086be78-ec3c-43cc-b799-5180a71e19f1
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# 방법: 서비스 등록
MPF\(관리 패키지 프레임워크\)는 관리되는 서비스의 등록을 제어하는 특성을 제공합니다. RegPkg 유틸리티는 이러한 특성을 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 서비스를 등록합니다.  
  
## 예제  
 아래 코드는 [VSSDK 샘플](../misc/vssdk-samples.md)에서 가져온 것입니다.  
  
 [!code-vb[VSSDKRegisterService#1](../misc/codesnippet/VisualBasic/how-to-register-a-service_1.vb)]
 [!code-cs[VSSDKRegisterService#1](../misc/codesnippet/CSharp/how-to-register-a-service_1.cs)]  
  
 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>는 SMyGlobalService 서비스를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 등록합니다.<xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> 및 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>에 대한 자세한 내용은 [Vspackage를 등록 및 등록 취소](../extensibility/registering-and-unregistering-vspackages.md)을 참조하세요.  
  
 이름이 같은 다른 서비스를 대체하는 서비스를 등록하려면 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 대신 <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>를 사용합니다.  
  
## 강력한 프로그래밍  
 서비스 클라이언트를 변경하지 않고 서비스 공급자를 더 쉽게 다시 컴파일할 수 있게 하거나 그 반대로 하려면 별도 어셈블리 모듈에서 서비스와 해당 인터페이스를 정의할 수 있습니다. 다음 코드는 Reference.Services\(C\#\) 샘플의 IMyGlobalService.cs 파일에서 가져온 것입니다.  
  
 [!code-vb[VSSDKRegisterService#2](../misc/codesnippet/VisualBasic/how-to-register-a-service_2.vb)]
 [!code-cs[VSSDKRegisterService#2](../misc/codesnippet/CSharp/how-to-register-a-service_2.cs)]  
  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>는 비관리 코드에서 인터페이스를 가져오는 데 필요합니다.  
  
> [!NOTE]
>  서비스와 인터페이스 둘 다에 동일한 형식 또는 GUID를 사용할 수 있지만 서비스에서 다른 인터페이스를 노출할 수 있으므로 두 가지를 구분하는 것이 좋습니다.  
  
## 참고 항목  
 [Registering VSPackages](http://msdn.microsoft.com/ko-kr/31e6050f-1457-4849-944a-a3c36b76f3dd)   
 [서비스 Essentials](../extensibility/internals/service-essentials.md)