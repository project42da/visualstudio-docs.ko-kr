---
title: "IDiaSourceFile::get_checksumType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSourceFile::get_checksumType 메서드"
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSourceFile::get_checksumType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

체크섬 형식을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 체크섬 형식을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 체크섬 형식 체크섬 알고리즘으로 매핑할 수 있는 값입니다.  예를 들어, 표준 PDB 파일 형식 일반적으로 다음 값 중 하나일 수 있습니다.  
  
|체크섬 유형|CryptoAPI 레이블|설명|  
|------------|-------------------|--------|  
|0|\<none\>|체크섬이 존재 합니다.|  
|1|`CALG_MD5`|MD5 해시 알고리즘으로 생성 된 검사 값입니다.|  
|2|`CALG_SHA1`|SHA1 해시 알고리즘으로 생성 된 검사 값입니다.|  
  
 `CryptoAPI` 레이블을 수에서 `ALG_ID` 열거형입니다.  해시 알고리즘에 대 한 자세한 내용은 참조는 `CryptoAPI` microsoft 섹션 [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)].  
  
 소스 파일에 대 한 실제 체크섬 바이트를 얻으려면 호출의 [IDiaSourceFile::get\_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) 방법입니다.  
  
## 참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get\_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)