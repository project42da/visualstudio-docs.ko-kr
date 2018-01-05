---
title: "속성 &lt;속성 이름&gt; 삭제할 수 없습니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 5bba0739a35dbc90c0c9141619c54b93f653d482
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>속성 &lt;속성 이름&gt; 삭제할 수 없습니다
속성 \<속성 이름 >으로 설정 되어 있으므로 삭제할 수 없습니다는 **판별자 속성** 간 상속 \<클래스 이름 > 및 \<클래스 이름 >  
  
 선택한 속성으로 설정 됩니다는 **판별자 속성** 오류 메시지에 표시 된 클래스 간 상속 합니다. 속성이 데이터 클래스 간 상속 구성에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 설정의 **판별자 속성** 하면 원하는 속성을 삭제할 수 데이터 클래스의 다른 속성에 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  O/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 상속 선을 선택합니다.  
  
2.  설정의 **판별자** 속성을 다른 속성입니다.  
  
3.  속성 삭제를 다시 한 번 시도합니다.  
  
## <a name="see-also"></a>참고 항목
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)