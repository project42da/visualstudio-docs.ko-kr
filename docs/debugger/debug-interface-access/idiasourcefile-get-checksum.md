---
title: "IDiaSourceFile::get_checksum | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSourceFile::get_checksum 메서드"
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSourceFile::get_checksum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

체크섬 바이트를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### 매개 변수  
 `cbData`  
 \[in\] 데이터 버퍼에서 바이트 단위의 크기입니다.  
  
 `pcbData`  
 \[out\] 체크섬의 바이트 수를 반환합니다.  이 매개 변수는 `NULL`일 수 없습니다.  
  
 `data`  
 \[in, out\] 체크섬 바이트를 입력 하는 버퍼입니다.  이 매개 변수가 `NULL`, 다음 `pcbData` 는 데 필요한 바이트 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 체크섬 바이트를 생성 하는 데 사용 된 체크섬 알고리즘 유형을 확인 하려면 호출을 [IDiaSourceFile::get\_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md) 메서드.  
  
 체크섬 체크섬 바이트의 변경 내용을 원본 파일의 변경 내용을 반영 됩니다 이미지의 원본 파일에서 일반적으로 생성 됩니다.  체크섬 바이트를 일치 하지 않는 경우 파일이 간주 됩니다 다음 로드 된 이미지 파일을 생성 하는 체크섬이 손상 되거나 변경 됩니다.  
  
 일반적인 체크섬 절대로 32 바이트의 크기 보다 하지만 검사 값의 최대 크기는 가정 하지 마십시오.  설정에서 `data` 매개 변수를 `NULL` 체크섬을 검색 하는 데 필요한 바이트 수를 가져올 수 있습니다.  적절 한 크기의 버퍼를 할당 하 고 새 버퍼를 다시 한 번이 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get\_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)