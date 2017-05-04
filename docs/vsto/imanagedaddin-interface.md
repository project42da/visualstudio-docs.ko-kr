---
title: "IManagedAddin 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "IManagedAddin 인터페이스"
ms.assetid: 5350629c-6cf8-42dd-ae65-3f34322ee10f
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# IManagedAddin 인터페이스
  관리되는 VSTO 추가 기능을 로드하는 구성 요소를 만들려면 IManagedAddin 인터페이스를 구현합니다. 이 인터페이스는 2007 Microsoft Office 시스템에서 추가되었습니다.  
  
## 구문  
  
```  
[  
    object,  
    uuid(B9CEAB65-331C-4713-8410-DDDAF8EC191A),  
    pointer_default(unique),  
    oleautomation  
]  
interface IManagedAddin : IUnknown  
{  
    HRESULT Load(  
        [in] BSTR bstrManifestURL,   
        [in] IDispatch *pdispApplication);  
    HRESULT Unload();  
};  
```  
  
## 메서드  
 다음 표에서는 IManagedAddin 인터페이스에서 정의한 메서드를 보여 줍니다.  
  
|이름|설명|  
|--------|--------|  
|[IManagedAddin::Load](../vsto/imanagedaddin-load.md)|Microsoft Office 응용 프로그램에서 관리되는 VSTO 추가 기능을 로드할 때 호출됩니다.|  
|[IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)|Microsoft Office 응용 프로그램에서 관리되는 VSTO 추가 기능을 언로드하기 직전에 호출됩니다.|  
  
## 설명  
 Microsoft Office 응용 프로그램은 2007 Microsoft Office 시스템부터 IManagedAddin 인터페이스를 사용하여 Office VSTO 추가 기능을 로드합니다. VSTO 추가 기능 로더\(VSTOLoader.dll\) 및 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 사용하지 않고 IManagedAddin 인터페이스를 구현하여 자체 VSTO 추가 기능 로더 및 관리되는 VSTO 추가 기능용 런타임을 만들 수 있습니다. 자세한 내용은 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)을 참조하세요.  
  
## 관리되는 추가 기능 로드 방법  
 다음 단계는 응용 프로그램을 시작할 때 발생합니다.  
  
1.  응용 프로그램에서는 다음 레지스트리 키에서 항목을 검색하여 VSTO 추가 기능을 찾습니다.  
  
     HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\*\<응용 프로그램 이름\>*\\Addins\\  
  
     이 레지스트리 키의 각 항목은 VSTO 추가 기능의 고유 ID입니다. 일반적으로 VSTO 추가 기능 어셈블리의 이름입니다.  
  
2.  응용 프로그램은 각 VSTO 추가 기능에 대한 항목에서 `Manifest` 항목을 찾습니다.  
  
     관리되는 VSTO 추가 기능은 매니페스트의 전체 경로를 HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\*\<응용 프로그램 이름\>*\\Addins\\*\<추가 기능 ID\>*의 `Manifest` 항목에 저장할 수 있습니다. 매니페스트는 VSTO 추가 기능을 로드하는 데 사용되는 정보를 제공하는 파일\(일반적으로 XML 파일\)입니다.  
  
3.  응용 프로그램에서 `Manifest` 항목을 찾으면 관리되는 VSTO 추가 기능 로더 구성 요소를 로드하려고 합니다. 응용 프로그램은 IManagedAddin 인터페이스를 구현하는 COM 개체를 만들어 이 작업을 수행합니다.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에 VSTO 추가 기능 로더 구성 요소\(VSTOLoader.dll\)가 포함되거나, IManagedAddin 인터페이스를 구현하여 직접 만들 수 있습니다.  
  
4.  응용 프로그램은 [IManagedAddin::Load](../vsto/imanagedaddin-load.md) 메서드를 호출하여 `Manifest` 항목의 값을 전달합니다.  
  
5.  [IManagedAddin::Load](../vsto/imanagedaddin-load.md) 메서드는 로드 중인 VSTO 추가 기능을 위한 보안 정책 및 응용 프로그램 도메인을 구성하는 등 VSTO 추가 기능을 로드하는 데 필요한 작업을 수행합니다.  
  
 Microsoft Office 응용 프로그램에서 관리되는 VSTO 추가 기능을 검색 및 로드하는 데 사용하는 레지스트리 키에 대한 자세한 내용은 [VSTO 추가 기능에 대한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)를 참조하세요.  
  
## IManagedAddin 구현 참고 자료  
 IManagedAddin을 구현하는 경우 다음 CLSID를 사용하여 구현이 포함된 DLL을 등록해야 합니다.  
  
 99D651D7\-5F7C\-470E\-8A3B\-774D5D9536AC  
  
 Microsoft Office 응용 프로그램에서는 이 CLSID를 사용하여 IManagedAddin를 구현하는 COM 개체를 만듭니다.  
  
> [!CAUTION]  
>  이 CLSID는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 VSTOLoader.dll에 의해서도 사용됩니다. 그러므로 IManagedAddin을 사용하여 자체 VSTO 추가 기능 로더 및 런타임 구성 요소를 만든 경우 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 사용하는 VSTO 추가 기능을 실행 중인 컴퓨터에 구성 요소를 배포할 수 없습니다.  
  
## 참고 항목  
 [관리되지 않는 API 참조&#40;Visual Studio에서 Office 개발&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
  
  