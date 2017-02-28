---
title: "Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
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
ms.sourcegitcommit: ae6564f10ca561853444698665779bd1014d4afd
ms.openlocfilehash: 2915a9ceec638471ac29599992a7ccdff17cefb4
ms.lasthandoff: 02/22/2017

---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드
새로운 Visual Studio 버전으로 전환할 때는 이전 버전에서 만든 솔루션, 프로젝트, 파일 및 기타 자산을 최신 버전에서 실행하기 *전에* 수정해야 하는지를 확인하고자 할 것입니다.

 널리 사용되는 대부분의 자산은 최신 버전인 Visual Studio 2017 RC에서도 가장 최근 버전인 Visual Studio 2015에서와 동일하게 동작합니다. 또한 이전 버전인 Visual Studio 2013 및 Visual Studio 2012에서도 동일하게 동작합니다.

 예를 들어 Visual Studio 2017 RC에서는 Visual Studio 2015 또는 Visual Studio 2013에서 만든 프로젝트를 열고 변경한 후 Visual Studio 2017 RC에서 다시 열 수 있습니다. 이 경우 변경 내용은 유지되고 이전 버전에서와 동일하게 프로젝트가 동작합니다. Visual Studio 2012에서 만든 여러 자산의 경우에도 마찬가지입니다.  

 Visual Studio 2013, Visual Studio 2012 또는 Visual Studio 2010 SP1과 함께 Visual Studio 2015를 사용하는 경우에는 이러한 모든 버전에서 프로젝트와 파일을 만들고 수정할 수 있습니다. 특정 버전에서 지원되지 않는 기능을 추가하지 않는 한 버전 간에 프로젝트와 파일을 이동할 수 있습니다. 특정 버전과 관련된 기능에 대한 자세한 내용은 [릴리스 정보](https://www.visualstudio.com/vs/release-notes/)를 참조하세요.

