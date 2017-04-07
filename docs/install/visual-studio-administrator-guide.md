---
title: "Visual Studio 관리자 가이드 | Microsoft 문서"
ms.custom: 
ms.date: 03/07/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 69ac1327fa9233bf0ecc18be5e7d2f2a4f82b3b0
ms.lasthandoff: 03/07/2017

---
# <a name="visual-studio-administrator-guide-for-visual-studio-2017"></a>Visual Studio 2017용 Visual Studio 관리자 가이드

각 대상 컴퓨터가 [최소 설치 요구 사항](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)을 충족하기만 하면 Visual Studio를 네트워크에 배포할 수 있습니다. [Visual Studio의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md) 페이지에서 설명한 대로 --layout 스위치를 사용하여 설치 파일을 실행한 다음 로컬 컴퓨터에서 네트워크 공유로 복사하여 네트워크 공유를 만들 수 있습니다.   

 네트워크 공유에서 설치하는 경우 소스 위치가 "기억"됩니다. 이는 클라이언트 컴퓨터 복구 시 클라이언트가 원래 설치된 네트워크 공유로 돌아가야 할 수도 있음을 의미합니다. 조직에서 Visual Studio 2017 클라이언트를 실행하는 예상 수명에 맞도록 네트워크 위치를 신중하게 선택합니다.

## <a name="tools"></a>도구

 Visual Studio 설치를 관리하는 데 도움이 되는 다음의 몇 가지 도구가 제공됩니다.

* [VS-Setup-Samples](https://github.com/microsoft/vs-setup-samples): C# 및 C++ 샘플을 사용하면 사용자가 자신의 컴퓨터에서 VS 인스턴스에 대한 정보를 얻을 수 있습니다.
* [VSWhere](https://github.com/microsoft/vswhere): C++ .exe를 사용하면 핵심적인 Visual Studio 도구를 찾을 수 있습니다.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): 일반적인 설치 관련 관리 작업을 위한 강력한 PowerShell 스크립트입니다.


## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 2017의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)
* [Visual Studio 작업 및 구성 요소 ID를 사용하여 오프라인 설치 사용자 지정](workload-and-component-ids.md)
* [Visual Studio 2017의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

