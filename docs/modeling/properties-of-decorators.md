---
title: "속성 데코레이터의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 95338b26019a2faf2afc2eb6be019ac33d6ece3c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-decorators"></a>데코레이터의 속성
데코레이터는 아이콘, 텍스트 또는 셰이프 또는 연결선 다이어그램에 표시할 수 있는 확장/축소 펼침 단추입니다. 다음 표에서 세 가지 데코레이터에 대 한 속성을 나타냅니다. 속성의 일부 셰이프 데코레이터에 대해서만 또는 커넥터 데코레이터에 대해서만 표시 됩니다.  
  
 자세한 내용은 참조 [도메인 특정 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
## <a name="expandcollapse-decorator"></a>Decorator 확장/축소  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|DisplayName|생성 된 디자이너에서 표시 되는 데코레이터의 이름입니다.|확장 축소 Decorator|  
|name|Decorator의 이름입니다.|ExpandCollapseDecorator|  
|노트|이 decorator와 관련 된 비공식 정보입니다.|\<none>|  
|HorizontalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 가로 오프셋입니다. (셰이프에 합니다.)|0|  
|VerticalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 세로 오프셋입니다. (셰이프에 합니다.)|0|  
|OffsetFromLine|인치에서의 기본 위치를 기준으로 줄에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|OffsetFromShape|인치에서의 기본 위치에 상대적인 셰이프에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|위치|Decorator의 기본 위치입니다.|SourceTop|  
  
## <a name="icon-decorator"></a>Decorator 아이콘  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|DefaultIcon|표시할 아이콘 또는 이미지 파일의 경로입니다.|\<none>|  
|DisplayName|생성 된 디자이너에 표시할 데코레이터의 이름입니다.|Decorator 아이콘|  
|name|Decorator의 이름입니다.|IconDecorator|  
|노트|Decorator와 관련 된 비공식 정보입니다.|\<none>|  
|HorizontalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 가로 오프셋입니다. (셰이프에 합니다.)|0|  
|VerticalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 세로 오프셋입니다. (셰이프에 합니다.)|0|  
|OffsetFromLine|인치에서의 기본 위치를 기준으로 줄에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|OffsetFromShape|인치에서의 기본 위치에 상대적인 셰이프에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|위치|Decorator의 기본 위치입니다.|SourceTop|  
  
## <a name="textdecorator"></a>TextDecorator  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|DefaultText|표시할 기본 텍스트입니다.|레이블|  
|DisplayName|생성 된 디자이너에 표시할 데코레이터의 이름입니다.|레이블|  
|FontSize|Decorator에 표시 되는 텍스트에 대 한 글꼴 크기입니다.|8|  
|FontStyle|Decorator에 표시 되는 텍스트에 대 한 글꼴 스타일입니다.|기본|  
|name|Decorator의 이름입니다.|레이블|  
|노트|Decorator와 관련 된 비공식 정보입니다.|\<none>|  
|HorizontalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 가로 오프셋입니다. (셰이프에 합니다.)|0|  
|VerticalOffset|인치에서는 데코레이터의 기본 위치를 기준으로 세로 오프셋입니다. (셰이프에 합니다.)|0|  
|OffsetFromLine|인치에서의 기본 위치를 기준으로 줄에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|OffsetFromShape|인치에서의 기본 위치에 상대적인 셰이프에서 데코레이터의 오프셋입니다. (On 커넥터만 합니다.)|0|  
|위치|Decorator의 기본 위치입니다.|TargetBottom|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)