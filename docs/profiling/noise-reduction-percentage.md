---
title: "노이즈 감소 백분율 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.filter"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 노이즈 감소 백분율"
ms.assetid: 1c10cd4c-2fdd-48c9-b562-a334b3b2df6c
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 노이즈 감소 백분율
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 노이즈 감소 백분율 설정의 값은 2입니다.  포괄 시간의 백분율이 이 설정보다 크거나 같은 항목만 호출 트리에 표시됩니다.  이 설정을 변경하여 호출 트리에 표시되는 항목 수를 제어할 수 있습니다.  예를 들어 값을 10으로 변경하면 포괄 시간이 10%보다 크거나 같은 호출 트리 항목만 표시됩니다.  설정 값을 늘리면 프로세스의 성능에 좀더 큰 영향을 주는 항목에 초점을 맞출 수 있습니다.