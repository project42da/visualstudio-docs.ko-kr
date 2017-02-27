---
title: "IDiaSession::findLinesByLinenum | Microsoft Docs"
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
  - "IDiaSession::findLinesByLinenum 메서드"
ms.assetid: 76d5622d-9a91-4c2a-a98f-263af5d1daef
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSession::findLinesByLinenum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 줄 번호 소스 파일에서 내에서 또는 가까운 밑에 컴파일 대상의 줄 번호를 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findLinesByLinenum (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `compiland`  
 \[in\] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 컴파일 대상에 있는 줄 번호에 대 한 검색을 나타내는 개체입니다.  이 매개 변수는 `NULL`일 수 없습니다.  
  
 `file`  
 \[in\] [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 에서 검색 하려면 원본 파일을 나타내는 개체입니다.  이 매개 변수는 `NULL`일 수 없습니다.  
  
 `linenum`  
 \[in\] 1부터 시작 하는 줄 번호를 지정합니다.  
  
> [!NOTE]
>  모든 줄을 지정 하려면 0을 사용할 수 없습니다 \(사용 하는 [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md) 모든 줄을 찾는 방법\).  
  
 `column`  
 \[in\] 열 수를 지정 합니다.  0을 사용 하 여 모든 열을 지정 합니다.  열 줄에 대 한 바이트 오프셋입니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 줄 번호 목록을 포함 하는 objta를 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제에 원본 파일을 열고이 파일에서 멤버 컴파일 대상을 열거 하 고 각 컴파일 시작 되는 위치는 소스 파일에서 줄 번호를 찾습니다.  
  
```cpp#  
void ShowLinesInCompilands(IDiaSession *pSession, LPCOLESTR filename)  
{  
    IDiaEnumSourceFiles* pEnum;  
    IDiaSourceFile*      pFile;  
    DWORD                celt;  
  
    pSession->findFile ( NULL, filename, nsFNameExt, &pEnum );  
    while ( pEnum->Next ( 1, &pFile, &celt ) == S_OK ) // for each file  
    {  
        IDiaEnumSymbols* pEnumCompilands;  
        IDiaSymbol* pCompiland;  
  
        pFile->get_compilands ( &pEnumCompilands );  
        // for each compiland  
        while ( pEnumCompilands->Next ( 1, &pCompiland, &celt ) == S_OK )  
        {  
            IDiaEnumLineNumbers* pEnum;  
            // Find first compiland closest to line 1 of the file.  
            if (pSession->findLinesByLinenum( pCompiland, pFile, 1, 0, &pEnum ) == S_OK)  
            {  
                IDiaLineNumber *pLineNumber;  
                DWORD lineCount;  
                while ( pEnum->Next(1,&pLineNumber,&lineCount) == S_OK)  
                {  
                     DWORD lineNum;  
                     if (pLineNumber->get_line(&lineNum) == S_OK)  
                     {  
                          printf("compiland starts in source at line number = %lu\n",lineNum);  
                     }  
                }  
            }  
        }  
    }  
}  
```  
  
## 참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)