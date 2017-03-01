---
title: "다른 Visual Studio 버전에서 모델 및 다이어그램 읽기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- models, versions of Visual Studio
ms.assetid: 46eee279-a9e4-4742-a024-5bd2cf032b86
caps.latest.revision: 20
author: alexhomer1
ms.author: ahomer
manager: douge
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
translationtype: Machine Translation
ms.sourcegitcommit: 8f84f22444a5df5b9f4f4af44cd8ee9136403467
ms.openlocfilehash: 9ffc4c39dee2da1d6daa051f478eac18d9670151
ms.lasthandoff: 02/22/2017

---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>다른 Visual Studio 버전에서 모델 및 다이어그램 읽기
모델 생성을 지원하지 않는 Visual Studio 버전에서 모델을 열면 읽기 전용 모드로 모델이 열립니다. 이 모드에서는 다이어그램의 레이아웃을 변경할 수 있지만 모델을 변경할 수는 없습니다.  
  
 모델 생성을 지 원하는 Visual Studio의 버전을 확인 하려면 참조 [아키텍처 및 모델링 도구에 대 한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)합니다.  
  
## <a name="obtaining-access-to-a-model-and-diagrams"></a>모델 및 다이어그램에 대한 액세스 권한 얻기  
 종속성 다이어그램을 읽으려면 먼저 Visual Studio를 사용 하 여 모델링 프로젝트를 열고 하며 다음 그 안에서 다이어그램을 엽니다.  
  
 이러한 이유로 종속성 다이어그램을 읽으려는 경우 생성 된 모델링 프로젝트에 대 한 액세스 권한이 있어야도. 이 작업을 수행하려면 [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]에서 프로젝트에서 액세스하거나 프로젝트 파일의 복사본을 가져옵니다.  
  
> [!NOTE]
>  코드 맵 및 코드에서 생성된 .NET 클래스 다이어그램에는 적용되지 않습니다. 이러한 다이어그램은 모델링 프로젝트와 독립적으로 볼 수 있습니다.  
  
 종속성 다이어그램을 읽으려면 하고자 하는 파일의 최소 집합은 다음과 같습니다.  
  
-   두 개의 다이어그램 파일을 읽고 싶은, 예를 들어 다이어그램 **MyDiagram.classdiagram 및 MyDiagram.classdiagram.layout**합니다.  
  
    > [!NOTE]
    >  종속성 다이어그램에 대 한 있어야 라는 파일이 *MyDiagram***. layerdiagram.suppressions**합니다.  
  
-   모델링 프로젝트 파일 (**MyModel.modelproj**)  
  
-   루트 모델 파일 (**ModelDefinition\MyModel.uml**)  
  
-   다이어그램에서 참조 하는 모든 패키지에 패키지 파일 (**ModelDefinition\MyPackage.uml**)  
  
## <a name="changes-that-you-can-make-in-read-only-mode"></a>읽기 전용 모드에서 수행할 수 있는 변경 내용  
 모델 생성을 지원하지 않는 Visual Studio 버전에서 모델 및 다이어그램을 열면 모델을 변경할 수 없습니다. 즉, 다이어그램이나 모델 탐색기에 표시되는 요소 및 관계를 변경할 수 없습니다. 그러나 다음과 같이 다이어그램의 레이아웃을 일부 변경할 수 있습니다.  
  
-   다이어그램에서 모양 및 연결선을 다시 정렬합니다.  
  
-   모양을 확장 및 축소합니다.  
  
 이러한 변경 내용을 저장할 수 있습니다. 변경 내용을 다른 사용자가 볼 수 있게 하려는 경우 적어도 보내야 업데이트 된 **.layout** 파일입니다.  
  
##  <a name="a-namerelatedtopicsa-related-topics"></a><a name="RelatedTopics"></a>관련된 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)|레이어 다이어그램에는 기존 아키텍처 또는 제안된 아키텍처의 구조가 표시됩니다. 코드가 작성되면 레이어 다이어그램에 대해 자동으로 유효성을 검사할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [앱용 모델 만들기](../modeling/create-models-for-your-app.md)
