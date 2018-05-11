---
title: IManagedAddin 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IManagedAddin interface
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d626257d3a2683a6fbb6032e8053572fd1301645
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="imanagedaddin-interface"></a>IManagedAddin 인터페이스
  VSTO 추가 기능 관리 하는 로드 하는 구성 요소를 만드는 IManagedAddin 인터페이스를 구현 합니다. 이 인터페이스는 2007 Microsoft Office 시스템에서 추가되었습니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="methods"></a>메서드  
 다음 표에서 IManagedAddin 인터페이스에서 정의한 메서드를 보여 줍니다.  
  
|이름|설명|  
|----------|-----------------|  
|[IManagedAddin::Load](../vsto/imanagedaddin-load.md)|Microsoft Office 응용 프로그램에서 관리되는 VSTO 추가 기능을 로드할 때 호출됩니다.|  
|[IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)|Microsoft Office 응용 프로그램에서 관리되는 VSTO 추가 기능을 언로드하기 직전에 호출됩니다.|  
  
## <a name="remarks"></a>설명  
 Microsoft Office 응용 프로그램은 2007 Microsoft Office 시스템부터 IManagedAddin 인터페이스를 사용 하 여 Office VSTO 추가 기능 로드를 돕기 위해 합니다. 사용자 고유의 VSTO 추가 기능 로더를 만들려는 IManagedAddin 인터페이스를 구현할 수 있습니다 및을 위해 런타임에 VSTO 추가 기능에서는 VSTO 추가 기능 로더 (VSTOLoader.dll)을 사용 하는 대신 관리 및 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 자세한 내용은 [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)을 참조하세요.  
  
## <a name="how-managed-add-ins-are-loaded"></a>관리되는 추가 기능 로드 방법  
 다음 단계는 응용 프로그램을 시작할 때 발생합니다.  
  
1.  응용 프로그램에서는 다음 레지스트리 키에서 항목을 검색하여 VSTO 추가 기능을 찾습니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\Office\\*\<응용 프로그램 이름 >* \Addins\  
  
     이 레지스트리 키의 각 항목은 VSTO 추가 기능의 고유 ID입니다. 일반적으로 VSTO 추가 기능 어셈블리의 이름입니다.  
  
2.  응용 프로그램은 각 VSTO 추가 기능에 대한 항목에서 `Manifest` 항목을 찾습니다.  
  
     관리 되는 VSTO 추가 기능에 대 한 매니페스트의 전체 경로 저장할 수는 `Manifest` HKEY_CURRENT_USER\Software\Microsoft\Office 항목\\*\<응용 프로그램 이름 >* \Addins\\  *\<ID 추가 기능에서 >* 합니다. 매니페스트는 VSTO 추가 기능을 로드하는 데 사용되는 정보를 제공하는 파일(일반적으로 XML 파일)입니다.  
  
3.  응용 프로그램에서 `Manifest` 항목을 찾으면 관리되는 VSTO 추가 기능 로더 구성 요소를 로드하려고 합니다. 응용 프로그램을 IManagedAddin 인터페이스를 구현 하는 COM 개체를 만들어이 수행 합니다.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 는 VSTO 추가 기능 로더 구성 요소 (VSTOLoader.dll)을 포함 하거나 IManagedAddin 인터페이스를 구현 하 여 직접 만들 수 있습니다.  
  
4.  응용 프로그램은 [IManagedAddin::Load](../vsto/imanagedaddin-load.md) 메서드를 호출하여 `Manifest` 항목의 값을 전달합니다.  
  
5.  [IManagedAddin::Load](../vsto/imanagedaddin-load.md) 메서드는 로드 중인 VSTO 추가 기능을 위한 보안 정책 및 응용 프로그램 도메인을 구성하는 등 VSTO 추가 기능을 로드하는 데 필요한 작업을 수행합니다.  
  
 레지스트리에 대 한 자세한 내용은 Microsoft Office 응용 프로그램 검색 하 고 로드를 사용 하는 키 관리 되는 VSTO 추가 기능을 참조 하십시오. [VSTO 추가 기능에 대 한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)합니다.  
  
## <a name="guidance-for-implementing-imanagedaddin"></a>IManagedAddin 구현 참고 자료  
 IManagedAddin 구현 하는 경우 다음 CLSID를 사용 하 여 구현이 포함 된 DLL을 등록 해야 합니다.  
  
 99D651D7-5F7C-470E-8A3B-774D5D9536AC  
  
 Microsoft Office 응용 프로그램이이 CLSID를 사용 하 여 IManagedAddin 구현 하는 COM 개체를 만듭니다.  
  
> [!CAUTION]  
>  이 CLSID는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 VSTOLoader.dll에 의해서도 사용됩니다. 따라서 IManagedAddin를 사용 하 여 사용자 고유의 VSTO 추가 기능 로더 및 런타임 구성 요소를 만들 경우 배포할 수 없습니다 구성 요소는 VSTO 추가 기능을 사용 하는 실행 중인 컴퓨터에는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되지 않는 API 참조 &#40;Visual Studio에서 Office 개발&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
  
  