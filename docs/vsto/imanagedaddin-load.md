---
title: 'Imanagedaddin:: Load | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 3faf9312-8ab4-4960-b2e7-8ca9859a3dcf
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 62c1af72158c0b416942e9124003dbeb06b584ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  관리되는 VSTO 추가 기능이 로드되면 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Load([in] BSTR bstrManifestURL,   
             [in] IDispatch *pdispApplication);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*bstrManifestURL*|VSTO 추가 기능에 대한 매니페스트의 전체 경로입니다.|  
|*pdispApplication*|VSTO 추가 기능을 로드 하는 호스트 응용 프로그램을 나타내는 IDispatch 포인터입니다.|  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 매니페스트는 VSTO 추가 기능을 로드하는 데 사용되는 정보를 제공하는 파일(일반적으로 XML 파일)입니다. 예를 들어 매니페스트는 VSTO 추가 기능이 로드될 때 인스턴스화할 VSTO 추가 기능 어셈블리 및 진입점 클래스의 위치를 지정할 수 있습니다.  
  
 *bstrManifestURL* 의 값을 포함 하는 매개 변수는 `Manifest` 아래에 HKEY_CURRENT_USER\Software\Microsoft\Office 항목\\*\<응용 프로그램 이름 >*\Addins\\*\<ID 추가 기능에서 >* VSTO 추가 기능에 대 한 레지스트리 키입니다. 자세한 내용은 [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)을 참조하십시오.  
  
 [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) 메서드를 구현하여 로드되는 VSTO 추가 기능을 위한 응용 프로그램 도메인 및 보안 정책 구성 등의 작업을 수행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
  
  