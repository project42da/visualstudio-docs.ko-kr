---
title: "속성 &lt;속성 이름&gt; 연결에 참여 하기 때문에 삭제할 수 없습니다 &lt;association 이름이&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 44a83e15cd712fb98c697b68b1dccaea5d0caf99
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>속성 &lt;속성 이름&gt; 연결에 참여 하기 때문에 삭제할 수 없습니다 &lt;연결 이름&gt;
선택한 속성으로 설정 됩니다는 **연결 속성** 오류 메시지에 표시 된 클래스 간 연결에 대 한 합니다. 속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 설정의 **연결 속성** 하면 원하는 속성을 삭제할 수 데이터 클래스의 다른 속성에 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  O/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 연결 선을 선택합니다.  
  
2.  열려는 선을 두 번 클릭은 **연결 편집기** 대화 상자.  
  
3.  속성을 제거는 **연관 속성**합니다.  
  
4.  속성 삭제를 다시 한 번 시도합니다.  
  
## <a name="see-also"></a>참고 항목
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)