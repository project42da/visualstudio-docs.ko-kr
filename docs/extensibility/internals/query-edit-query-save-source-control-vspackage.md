---
title: "쿼리 (소스 제어 VSPackage) 저장 쿼리 편집 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "QEQS 이벤트"
  - "쿼리 이벤트 저장 쿼리 편집"
  - "소스 제어 패키지 이벤트 쿼리 편집 쿼리 저장"
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 쿼리 (소스 제어 VSPackage) 저장 쿼리 편집
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]편집기 쿼리 편집 쿼리 저장 \(QEQS\) 이벤트를 브로드캐스트할 수 있습니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]QEQS 이벤트는 받는 사람 수 있도록 소스 제어 스텁 QEQS 서비스를 구현 합니다.  이러한 이벤트 후 VSPackage 현재 활성 원본 컨트롤에 위임 하는.  VSPackage 구현 활성 소스 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 그 방법.  메서드는 `IVsQueryEditQuerySave2` 즉시 문서를 처음으로 한 문서를 저장 하기 전에 편집 되기 전에 인터페이스 라고 일반적으로 합니다.  
  
## QueryEditQuerySave 이벤트  
 VSPackage 소스 제어를 구현 하 여 QEQS 이벤트를 처리 합니다는 `IVsQueryEditQuerySave2` 인터페이스와 필요한 방법입니다.  아래는 VSPackage 최소한 구현 해야 하는 두 가지 방법에 대 한 간략 한 설명이 있습니다.  실제 구현은 소스 제어 모델의 논리에 따라 해야 합니다.  
  
### QueryEditFiles 메서드  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 모든 프로젝트 또는 편집기 파일을 수정 하려고 할 때 호출 됩니다.  이 메서드가 호출 되는 것이 좋습니다  *전* 파일을 수정 하 고 파일을 저장 합니다.  호출 하는 경우는 `IVsQueryEditQuerySave2::QueryEditFiles` 소스 제어에서 지정 된 파일 인지 여부에 체크 아웃 하는 데 필요한, 여부는 로드할 수 있는 메서드를 확인 합니다.  환경 파일 편집 되지 경우는 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드 호출 프로그램 편집을 취소 하려면 지시 합니다.  호출자가 호출 모드를 지정할 수도 있습니다.  만 표시 하는 UI를 발생 하지 않는 경우 "자동" 모드에서 동작이이 메서드를 사용 합니다.  UI를 피할 수 없는 경우의 문제를 나타내는 플래그를 반환 합니다.  
  
 트랜잭션 방식으로 동작 하는 메서드. 즉, 단일 파일에서 편집을 취소 하면 편집에 대 한 모든 파일이 취소 됩니다.  반대로 편집이 허용 된 경우, 모든 파일에 대해 허용 됩니다.  이 메서드는 지정 된 여러 파일을 한 번 편집 허용 하는 경우 항상 동일한 파일 집합에 대 한 후속 호출을 편집 허용 해야.  파일 종료, 저장 및 다시 로드 될 때까지 허용 편집 루프가 계속 됩니다. 해당 속성 \(등록 정보\)을 변경 하기 전까지. 또는 소스 제어 패키지 변경 될 때까지.  구현에서 고려해 야 할 경우 해당 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드에 특별 한 파일, 여러 파일, 사용자 및 메모리 내 편집을 취소 합니다.  
  
### QuerySaveFiles 메서드  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> 모든 프로젝트 또는 편집기 파일 집합을 저장 해야 할 때 호출 됩니다.  호출 될 경우는 `IVsQueryEditQuerySave2::QuerySaveFiles` 메서드를 읽기 전용으로 지정 된 파일에 있는 경우와 소스 제어에서 지 확인 합니다.  파일을 체크 아웃 해야 하는 경우 소스 제어 패키지를 통화 위임 됩니다.  환경 파일 저장 한 수 없는 경우는 `IVsQueryEditQuerySave2::QuerySaveFiles` 메서드 편집기 저장 작업을 취소할 수 있는 설명 합니다.  와 마찬가지로 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드를 것입니다 호출자가 호출 모드를 지정할 수 있습니다.  만 표시 하는 UI를 발생 하지 않는 경우 "자동" 모드에서 동작이이 메서드를 사용 합니다.  UI를 피할 수 없는 경우의 문제를 나타내는 플래그를 반환 합니다.  
  
 이 메서드는 트랜잭션 방식으로 동작 합니다. 즉, 저장 단일 파일에 저장을 취소 하는 경우 모든 파일에 대 한 취소 합니다.  반대로, 저장 허용 된 경우, 모든 파일에 대해 허용 되어야 합니다.  와 마찬가지로 `IVsQueryEditQuerySave2::QueryEditFiles` 의 구현을 고려해 야 하는 경우, 메서드는 `IVsQueryEditQuerySave2::QuerySaveFiles` 메서드에 특별 한 파일, 여러 파일, 사용자 및 메모리 내 편집을 취소 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>