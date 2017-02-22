---
title: "데코레이터의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 데코레이터"
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: 23
caps.handback.revision: 23
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 데코레이터의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Decorators 아이콘, 텍스트, 도형 또는 다이어그램의 연결선을 표시할 수 있는 확대\/축소: 데이터입니다.  다음 표에서 데코레이터의 세 가지 종류의 속성을 표시합니다.  속성의 일부 셰이프 decorators 또는 커넥터 decorators만에 표시 됩니다.  
  
 자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)를 참조하십시오.  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
## 데코레이터를 확장\/축소 합니다.  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|DisplayName|생성 된 디자이너에 표시 되는 데코레이터의 이름입니다.|축소 데코레이터를 확장 합니다.|  
|Name|데코레이터의 이름입니다.|ExpandCollapseDecorator|  
|참고|이 데코레이터와 관련 된 비공식 메모 합니다.|\<none\>|  
|HorizontalOffset|데코레이터, 인치에서 기본 위치를 기준으로 가로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|VerticalOffset|데코레이터, 인치에서 기본 위치에 상대적인 세로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|OffsetFromLine|데코레이터의 기본 위치, 인치에서를 기준으로 줄을 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|OffsetFromShape|데코레이터의 기본 위치, 인치에서를 기준으로 도형에서의 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|위치|기본 위치는 데코레이터입니다.|SourceTop|  
  
## 아이콘 데코레이터  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|DefaultIcon|표시 하는 아이콘 또는 이미지 파일의 경로입니다.|\<none\>|  
|DisplayName|생성 된 디자이너에 표시 되는 데코레이터의 이름입니다.|아이콘 데코레이터|  
|Name|데코레이터의 이름입니다.|IconDecorator|  
|참고|데코레이터와 관련 된 비공식 메모 합니다.|\<none\>|  
|HorizontalOffset|데코레이터, 인치에서 기본 위치를 기준으로 가로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|VerticalOffset|데코레이터, 인치에서 기본 위치에 상대적인 세로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|OffsetFromLine|데코레이터의 기본 위치, 인치에서를 기준으로 줄을 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|OffsetFromShape|데코레이터의 기본 위치, 인치에서를 기준으로 도형에서의 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|위치|기본 위치는 데코레이터입니다.|SourceTop|  
  
## TextDecorator  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|DefaultText|표시 하는 기본 텍스트입니다.|레이블|  
|DisplayName|생성 된 디자이너에 표시 되는 데코레이터의 이름입니다.|레이블|  
|FontSize|데코레이터에 표시 되는 텍스트의 글꼴 크기입니다.|8|  
|FontStyle|데코레이터에 표시 되는 텍스트의 글꼴 스타일입니다.|기본|  
|Name|데코레이터의 이름입니다.|레이블|  
|참고|데코레이터와 관련 된 비공식 메모 합니다.|\<none\>|  
|HorizontalOffset|데코레이터, 인치에서 기본 위치를 기준으로 가로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|VerticalOffset|데코레이터, 인치에서 기본 위치에 상대적인 세로 오프셋입니다.  \(도형에만 합니다.\)|0|  
|OffsetFromLine|데코레이터의 기본 위치, 인치에서를 기준으로 줄을 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|OffsetFromShape|데코레이터의 기본 위치, 인치에서를 기준으로 도형에서의 오프셋입니다.  \(커넥터에만 합니다.\)|0|  
|위치|기본 위치는 데코레이터입니다.|TargetBottom|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)