---
title: "N 계층 응용 프로그램에서 데이터 집합 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 2274ac9bcfd3ba7c87364f5c4c79cd155844fe73
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="work-with-datasets-in-n-tier-applications"></a>N 계층 응용 프로그램에서 데이터 집합 작업
*N 계층 데이터 응용 프로그램* 은 여러 논리 계층으로 분리 되어 있는 데이터 중심 응용 프로그램 (또는 *계층*). 다시 말해서 N 계층 데이터 응용 프로그램은 여러 프로젝트로 구분되며 데이터 액세스 계층, 비즈니스 논리 계층 및 표시 계층이 각 프로젝트에 포함되는 응용 프로그램입니다. 자세한 내용은 참조 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)합니다.  
  
TableAdapter 및 데이터 클래스를 개별 프로젝트로 생성할 수 있도록 형식화된 데이터 집합이 향상되었습니다. 따라서 응용 프로그램 계층을 빠르게 분리하고 N 계층 데이터 응용 프로그램을 생성하는 기능이 제공됩니다.  
  
형식화 된 데이터 집합에서 N 계층이 지원 되므로 n 계층 디자인에서 응용 프로그램 아키텍처의 반복적인 개발을 수 있습니다. 또한 둘 이상의 프로젝트로 코드를 수동 분리할 필요가 없어집니다. 사용 하 여 데이터 계층 디자인을 시작는 **데이터 집합 디자이너**합니다. 응용 프로그램 아키텍처는 n 계층 디자인 전환할 준비가 되 면 설정 된 **데이터 집합 프로젝트** dataset 클래스를 별도 프로젝트로 생성 하는 데이터 집합의 속성입니다.  
  
## <a name="reference"></a>참조  
<xref:System.Data.DataSet>  
<xref:System.Data.TypedTableBase%601>  
  
## <a name="see-also"></a>참고 항목
[N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)  
[연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  
[n 계층 응용 프로그램에서 TableAdapter에 코드 추가](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
[n 계층 응용 프로그램에서 데이터 집합에 코드 추가](../data-tools/add-code-to-datasets-in-n-tier-applications.md)  
[n 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)  
[데이터 집합 및 TableAdapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
[계층적 업데이트](../data-tools/hierarchical-update.md)  
[Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)  
[Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)  
[만들기 및 Tableadapter를 구성 합니다.](../data-tools/create-and-configure-tableadapters.md)  
[LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)