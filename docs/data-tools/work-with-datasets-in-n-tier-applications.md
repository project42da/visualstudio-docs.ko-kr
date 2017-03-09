---
title: "N 계층 응용 프로그램에서 데이터 집합 작업 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Basic], n 계층 응용 프로그램"
  - "데이터 집합 프로젝트[VS n 계층 응용 프로그램]"
  - "데이터 집합[Visual Basic], n 계층 응용 프로그램"
  - "분산 응용 프로그램[VS n 계층 응용 프로그램]"
  - "다중 계층 응용 프로그램"
  - "다중 계층 데이터베이스 응용 프로그램"
  - "n 계층 응용 프로그램"
  - "TableAdapter, n 계층 응용 프로그램"
  - "계층, n 계층 응용 프로그램"
  - "형식화된 데이터 집합, n 계층 응용 프로그램"
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
caps.latest.revision: 22
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# N 계층 응용 프로그램에서 데이터 집합 작업 작업
*N 계층 데이터 응용 프로그램*은 여러 논리 *계층*으로 구분되는 데이터 중심 응용 프로그램입니다.  다시 말해서 N 계층 데이터 응용 프로그램은 여러 프로젝트로 구분되며 데이터 액세스 계층, 비즈니스 논리 계층 및 표시 계층이 각 프로젝트에 포함되는 응용 프로그램입니다.  자세한 내용은 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)을 참조하십시오.  
  
 TableAdapter 및 데이터 클래스를 개별 프로젝트로 생성할 수 있도록 형식화된 데이터 집합이 향상되었습니다.  따라서 응용 프로그램 계층을 빠르게 분리하고 N 계층 데이터 응용 프로그램을 생성하는 기능이 제공됩니다.  
  
 형식화된 데이터 집합에서 N 계층이 지원되므로 N 계층 디자인에서 응용 프로그램 아키텍처의 반복적인 개발을 수행할 수 있으며, 코드를 둘 이상의 프로젝트로 코드를 수동 분리할 필요가 없습니다.  [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)를 사용하여 데이터 계층 디자인을 시작합니다.  응용 프로그램 아키텍처에 N 계층 디자인을 적용할 준비가 되면 데이터 집합 클래스를 별도의 프로젝트로 생성하도록 데이터 집합의 **데이터 집합 프로젝트** 속성을 설정합니다.  
  
## 단원 내용  
 [방법: 데이터 집합 및 TableAdapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
 생성된 데이터 집합 클래스를 생성된 TableAdapter 클래스를 포함하는 프로젝트에서 새 프로젝트로 이동하는 방법을 설명합니다.  
  
 [방법: N 계층 응용 프로그램에서 TableAdapter에 코드 추가](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
 N 계층 TableAdapter에 대해 코드를 추가할 수 있는 partial 클래스를 생성하는 방법을 설명합니다.  
  
 [방법: N 계층 응용 프로그램에서 데이터 집합에 코드 추가](../data-tools/add-code-to-datasets-in-n-tier-applications.md)  
 N 계층 데이터 집합에 대해 코드를 추가할 수 있는 partial 클래스를 생성하는 방법을 설명합니다.  
  
 [방법: N 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)  
 변경되는 데이터에 대해 유효성 검사를 수행할 코드의 추가 위치에 대해 설명합니다.  
  
 [연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  
 형식화된 데이터 집합을 만들고 TableAdapter 및 데이터 집합 코드를 여러 프로젝트로 분리하는 단계별 지침을 제공합니다.  
  
 [연습: N 계층 데이터 응용 프로그램에 유효성 검사 추가](../Topic/Walkthrough:%20Adding%20Validation%20to%20an%20N-Tier%20Data%20Application.md)  
 N 계층 데이터 응용 프로그램 연습에서 만든 응용 프로그램에 유효성 검사 기능을 추가하는 단계별 지침을 제공합니다.  
  
## 참조  
 <xref:System.Data.DataSet>  
  
 <xref:System.Data.TypedTableBase%601>  
  
## 관련 단원  
 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)  
  
 [계층적 업데이트](../data-tools/hierarchical-update.md)  
  
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)  
  
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)  
  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)  
  
 [LINQ to SQL을 사용하는 N 계층 및 원격 응용 프로그램](../Topic/N-Tier%20and%20Remote%20Applications%20with%20LINQ%20to%20SQL.md)