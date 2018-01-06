---
title: IManagedAddin::Unload | Microsoft Docs
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
helpviewer_keywords: Unload method
ms.assetid: 40a73f07-2605-4745-8ac5-0a0189167fd7
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b16478232faa2b34a6d8f93d2a53b69b0f76b871
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  관리되는 VSTO 추가 기능이 언로드되기 바로 전에 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Unload();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 버전의 Microsoft Office에서 호출되지 않습니다. @FSHO2@이 메서드는 나중에 사용할 수 있도록 예약되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
  
  