---
title: "보안 및 지역화된 위성 어셈블리 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
caps.latest.revision: 8
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 587b403257a5fadefd32e57ecdd9914bd60a9e26
ms.lasthandoff: 02/22/2017

---
# <a name="security-and-localized-satellite-assemblies"></a>보안 및 지역화된 위성 어셈블리
주 어셈블리에 강력한 이름 지정이 사용될 경우 주 어셈블리와 같은 개인 키를 사용하여 위성 어셈블리에 서명해야 합니다. 주 어셈블리와 위성 어셈블리 간에 공개/개인 키 쌍이 일치하지 않으면 리소스가 로드되지 않습니다. 어셈블리 서명에 대한 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](http://msdn.microsoft.com/Library/2c30799a-a826-46b4-a25d-c584027a6c67)을 참조하세요.  
  
 일반적으로 조직의 서명 그룹 또는 외부 서명 조직이 개인 키로 서명하도록 해야 할 수 있습니다. 이는 액세스가 보통 몇몇 개인으로 제한된다는 개인 키의 민감한 특성 때문입니다. 개발 중에 지연된 서명을 사용할 수 있습니다. 자세한 내용은 [어셈블리 서명 연기](http://msdn.microsoft.com/Library/9d300e17-5bf1-4360-97da-2aa55efd9070)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 보안 고려 사항](http://msdn.microsoft.com/Library/1b5439c1-f3d5-4529-bd69-01814703d067)   
 [주요 보안 개념](http://msdn.microsoft.com/Library/3cfced4f-ea02-4e66-ae98-d69286363e98)   
 [.NET Framework 기반의 국가별 응용 프로그램 소개](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [응용 프로그램 지역화](../ide/localizing-applications.md)   
 [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)
