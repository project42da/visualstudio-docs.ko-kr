---
title: 워크플로 디자이너-형식 컬렉션 편집기 대화 상자
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09bb5c7789be78a39a8d33a556ce66385db4a1d8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="type-collection-editor-dialog-box"></a>형식 컬렉션 편집기 대화 상자

**형식 컬렉션 편집기** 대화 상자에 알려진된 형식을 추가 하는 데 사용 됩니다는 **보낼** 및 **수신** 활동입니다. 이 대화 상자는 또한 제네릭 형식 인수를 추가할는 **InvokeMethod** 활동입니다. 에 사용 되는 경우는 **보낼** 및 **수신** 알려진된 형식을 추가 하는 활동의 **형식 컬렉션 편집기** 대화 상자에는 고유 하 게 추가 된 형식이 필요 합니다. 경우 중복 형식을 추가 하 고 클릭 하 여 변경을 커밋합니다 **확인**, 오류 메시지가 반환 됩니다. 에 사용 되는 경우는 **InvokeMethod** 활동에 제네릭 형식 인수 추가 **형식 컬렉션 편집기** 대화 상자에는 중복 형식 추가할 수 있습니다.

자세한 내용은 참조 [데이터 계약 알려진된 형식](/dotnet/framework/wcf/feature-details/data-contract-known-types)합니다.

다음 표에 사용자 인터페이스 (UI) 요소는 **형식 컬렉션** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**형식 목록**|추가 또는 제거된 형식의 목록입니다.|

## <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Send 및 Receive 활동에 대해 형식 컬렉션 편집기를 표시하려면

1.  선택 된 **보낼** 또는 **수신** 디자인 보기에서 작업 합니다.

2.  키를 눌러 **F4** 불러오는 **속성** 창.

3.  에 **속성** 창에서 줄임표 단추 옆에는 **KnownTypes** 속성입니다.

## <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>InvokeMethod 활동에 대해 형식 컬렉션 편집기를 표시하려면

1.  선택 된 **InvokeMethod** 디자인 보기에서 작업 합니다.

2.  키를 눌러 **F4** 불러오는 **속성** 창.

3.  에 **속성** 창에서 줄임표 단추 옆에는 **GenericTypeArguments** 속성입니다.