---
title: "편집기와 언어 서비스 확장 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 67d250a2806b367a76fa593026f10d4b671c21b2
ms.lasthandoff: 02/22/2017

---
# <a name="editor-and-language-service-extensions"></a>편집기와 언어 서비스 확장
Visual Studio 코드 편집기의 대부분의 기능을 확장할 수 있습니다. 편집기는 Windows Presentation Foundation (WPF)에 기반 하 고 관리 코드에서 기록 됩니다. 이 디자인에서 이전 버전의 Visual Studio의 디자인 달라 지는 않지만 대부분의 동일한 기능을 제공 합니다. 편집기를 확장 하려면는 프레임 워크 MEF (Managed Extensibility)를 사용 합니다.  
  
 라고 하는 어댑터를 제공 하는 Visual Studio SDK *shim* 이전 버전용으로 작성 된 Vspackage를 지원 하도록 합니다. 그럼에도 불구 하 고는 기존 VSPackage를 설정한 경우 더 나은 성능 및 안정성을 신기술을 업데이트 하는 것이 좋습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)|편집기 항목 템플릿을 사용 하 여를 소개 합니다.|  
|[편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)|문서에 링크를 디자인 및 코어 편집기의 기능을 소개 하 고 확장 하는 방법을 보여 줍니다.|  
|[편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)|기존 코드의 핵심 편집기에 액세스 하는 방법을 설명 하는 문서에 연결 되어 있습니다.|  
|[사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)|사용자 지정 편집기를 만드는 방법을 설명 하는 문서에 연결 합니다.|  
|[레거시 언어 서비스 확장](../extensibility/internals/legacy-language-service-extensibility.md)|프로그래밍 언어를 Visual Studio에 통합 하는 방법에 설명 하는 문서에 연결 되어 있습니다.|  
|[관리 되는 확장성 프레임 워크 (MEF)](http://msdn.microsoft.com/Library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|관리 되는 확장성 프레임 워크 (MEF)를 소개합니다.|  
|[Windows Presentation Foundation](http://msdn.microsoft.com/Library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Windows Presentation Foundation (WPF)을 소개합니다.|
