---
title: 코드 조각
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 0FE27C0C-A861-4133-A74E-8D0505CF5342
ms.openlocfilehash: 0f89c7eadb9f9fbc7a38f4100a6df259a1aa0a06
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="code-snippets"></a>코드 조각 

_코드 템플릿_이라고도 하는 코드 조각은 미리 작성된 코드 블록을 삽입하고 편집하여 프로그래밍의 능률을 높이는 데 유용합니다. 특히, 공통되는 패턴을 빠르게 추가하거나 개발자가 구문을 잘 모르는 새로운 패턴을 배울 때 코드 조각이 편리합니다. C#, F#, HTML, XML, Python 및 Razor용 템플릿이 제공됩니다.

이 섹션에서는 코드 조각을 만들고, 삽입하고, 사용하는 방법을 설명합니다.

## <a name="inserting-a-snippet"></a>코드 조각 삽입

다양한 방법으로 코드 조각을 추가할 수 있으며, 아래에서는 그중 일부를 설명합니다.
 
* **탭 확장** - 템플릿 이름을 입력할 때 목록에 나타나면 선택 후 **Tab** 키를 두 번 눌러 추가합니다.
 
  ![코드의 탭 확장](media/source-editor-image13.png)

* **도구 상자** - 도구 상자 패드를 사용하여 모든 코드 조각의 목록을 표시합니다. 도구 상자의 템플릿을 소스 코드에서 올바른 위치에 끌어 놓습니다.

 ![도구 상자의 코드 조각](media/source-editor-image14.png)

* **템플릿 삽입 명령** - 현재는 템플릿 삽입 기능에 설정된 기본 키 바인딩이 없습니다. 키 바인딩을 만들려면 **Visual Studio > 기본 설정... > 키 바인딩**으로 이동하고 `template`을 검색합니다. 이렇게 하면 [바인딩 편집] 필드에 원하는 키 바인딩을 추가한 다음 **적용**을 클릭할 수 있습니다.

 ![템플릿 삽입 명령](media/source-editor-image15.png)

## <a name="creating-a-new-template"></a>새 템플릿 만들기

다양한 언어로 작성된 수많은 기존 템플릿을 사용하고 편집할 수 있지만, **Visual Studio > 기본 설정 > 텍스트 편집기 > 코드 조각**으로 이동하여 새 템플릿을 추가할 수도 있습니다.

![새 템플릿 삽입](media/source-editor-image12.png)
