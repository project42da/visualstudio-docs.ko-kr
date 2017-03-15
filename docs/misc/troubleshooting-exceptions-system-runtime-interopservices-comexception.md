---
title: "예외 문제 해결: System.Runtime.InteropServices.COMException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHCOM"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "COMException 클래스"
ms.assetid: 14b6de51-e039-4db7-9321-06c9e16e328a
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Runtime.InteropServices.COMException
<xref:System.Runtime.InteropServices.COMException> 예외는 COM 메서드 호출에서 인식할 수 없는 HRESULT가 반환되는 경우에 throw됩니다.  
  
## 관련 팁  
 **예외의 ErrorCode 속성을 확인하면 COM 개체가 반환한 HRESULT를 확인할 수 있습니다.**  
 런타임에 알 수 없는 HRESULT를 발견하면 <xref:System.Runtime.InteropServices.COMException> 예외가 throw됩니다. 여기에는 호출에서 반환한 HRESULT가 들어 있는 공용 `ErrorCode` 속성이 포함됩니다. 런타임에서 사용할 수 있는 오류 메시지가 있으면 이 메시지가 호출자에 반환됩니다. 그러나 COM 구성 요소 개발자가 오류 메시지를 포함하지 않은 경우에는 런타임에서 메시지 문자열 대신 8자리 숫자로 구성된 HRESULT를 반환합니다. 호출자는 HRESULT를 통해 예외의 원인을 확인할 수 있습니다. 자세한 내용은 [방법: HRESULT 및 예외 매핑](../Topic/How%20to:%20Map%20HRESULTs%20and%20Exceptions.md)을 참조하세요.  
  
 **호스팅 프로세스를 비활성화합니다.**  
 COM은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]와 호스팅 프로세스 사이에 통신하는 데 사용됩니다. COM은 코드를 실행하기 전에 사용되므로 `CoInitializeSecurity`를 호출하면 이 예외가 throw됩니다.  
  
### 설명  
 CLR\(공용 언어 런타임\)에서는 잘 알려진 HRESULT를 .NET 예외로 변환하므로 COM 개체는 관리되는 클라이언트에 의미 있는 오류 정보를 반환할 수 있습니다. 관리되지 않는 클라이언트에 특정 HRESULT를 반환하면 반대로 예외를 HRESULT에 매핑할 수도 있습니다.  
  
 런타임에 바인딩된 매개 변수를 Microsoft Office 개체의 메서드에 전달하는 경우 이 개체가 COM 개체이면 <xref:System.Runtime.InteropServices.COMException> 예외가 throw될 수 있습니다. 런타임 바인더에서는 이러한 메서드 호출에 `ByRef` 매개 변수가 사용되는 것으로 간주하고 사용자가 전달한 속성에 `Set` 접근자가 있는 것으로 간주합니다. 이 속성에 해당 접근자가 없으면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서 <xref:System.MissingMethodException> 예외\(HRESULT CORE\_E\_MISSINGMETHOD\)가 생성됩니다. 이 문제를 해결하려면 초기 바인딩 개체를 사용하거나 개체의 속성 대신 변수를 전달합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.COMException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [COM Interop 예외 처리](../Topic/Handling%20COM%20Interop%20Exceptions.md)