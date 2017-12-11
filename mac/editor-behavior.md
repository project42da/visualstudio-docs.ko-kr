---
title: "편집기 동작 | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 3515dfbf3a7cf8c23178aa9df243638f955593e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="editor-behavior"></a>편집기 동작

작성된 대로 코드에 형식이 지정될 수 있도록 편집기 동작을 설정할 수 있습니다. 이러한 작업은 **Visual Studio > 기본 설정... > 텍스트 편집기 > 동작**에서 설정되며, 아래에서는 자주 사용하는 몇 가지 기능에 대해 설명합니다.

![편집기 동작 옵션](media/source-editor-image9.png)

*  새 클래스, 메서드 또는 속성을 만들 때 일치하는 닫는 중괄호를 코드에 자동으로 추가할 수 있습니다. 이 옵션을 선택한 경우 `{`를 입력하면 `}`가 자동으로 추가됩니다.
* 세미콜론 또는 중괄호와 같은 문자 누르기에 의해 즉석 코드 형식 지정이 트리거되어 설정된 형식 지정 기본 설정을 에뮬레이트합니다.
* 저장할 때 파일의 형식을 지정하도록 선택할 수도 있습니다. 이 경우 필요에 따라 코드를 작성할 수 있으며 IDE에서 기존 기본 설정에 따라 코드 형식을 지정합니다.
* 들여쓰기를 없음, 자동 또는 스마트로 설정할 수 있습니다. 각 옵션은 다음 작업을 수행합니다.
 * 없음 - 캐럿을 다음 줄의 시작 부분에 설정합니다.
 * 자동 - 캐럿을 다음 줄의 동일한 열에 설정합니다.
 * 스마트 - 코드에 따라 다음 줄을 들여씁니다.
* 단어 분리 동작은 OS마다 차이가 있으며, 탐색을 위해 텍스트 편집기에서 단어의 시작 위치나 끝 위치를 알아야 합니다. 형식 지정을 Unix 또는 Windows로 설정할 수 있습니다.

XML, CSS, HTML 및 JSON에 대한 형식 지정 규칙을 설정할 수도 있습니다.