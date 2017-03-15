---
title: "데모 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 샘플"
  - "데모 샘플[Visual Studio ALM]"
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# 데모 샘플
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 절차에서는 [연습: C\/C\+\+ 코드의 오류 분석](../Topic/Walkthrough:%20Analyzing%20C-C++%20Code%20for%20Defects.md)을 위한 샘플을 만드는 방법을 보여 줍니다.  이 절차에서는 다음 항목을 만듭니다.  
  
-   CppDemo라는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션  
  
-   CodeDefects라는 정적 라이브러리 프로젝트  
  
-   Annotations라는 정적 라이브러리 프로젝트  
  
 또한 이 절차에서는 헤더의 코드와 정적 라이브러리에 대한 .cpp 파일을 제공합니다.  
  
### CppDemo 솔루션 및 CodeDefects 프로젝트 만들기  
  
1.  **파일** 메뉴를 클릭하고 **새로 만들기**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
2.  Visual C\+\+가 VS의 기본 언어가 아니면 **프로젝트 형식** 트리 목록에서 **다른 언어**를 확장합니다.  
  
3.  **Visual C\+\+**를 확장하고 **일반**을 클릭합니다.  
  
4.  **템플릿**에서 **빈 프로젝트**를 클릭합니다.  
  
5.  **이름** 텍스트 상자에 **CodeDefects**를 입력합니다.  
  
6.  **솔루션용 디렉터리 만들기** 확인란을 선택합니다.  
  
7.  **솔루션 이름** 텍스트 상자에 **CppDemo**를 입력합니다.  
  
### CodeDefects 프로젝트를 정적 라이브러리로 구성  
  
1.  솔루션 탐색기에서 **CodeDefects**를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
2.  **구성 속성**을 확장한 다음 **일반**을 클릭합니다.  
  
3.  **일반** 목록에서 **대상 확장명** 옆의 열에 있는 텍스트를 선택하고 **.lib**를 입력합니다.  
  
4.  **프로젝트 기본값**에서 **구성 형식** 옆의 열을 클릭하고 **정적 라이브러리 \(.lib\)**를 클릭합니다.  
  
### CodeDefects 프로젝트에 헤더 및 소스 파일 추가  
  
1.  솔루션 탐색기에서 **CodeDefects**를 확장하고 **헤더 파일**을 마우스 오른쪽 단추로 클릭한 다음 **추가**를 클릭하고 **새 항목**을 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **코드**를 클릭한 다음 **헤더 파일 \(.h\)**을 클릭합니다.  
  
3.  **이름** 상자에 **Bug.cpp**를 입력한 다음 **추가**를 클릭합니다.  
  
4.  다음 코드를 복사하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기에서 **Bug.cpp** 파일에 붙여넣습니다.  
  
    ```  
    #include <windows.h>  
  
    //    
    //These 3 functions are consumed by the sample  
    //  but are not defined. This project cannot be linked!  
    //  
  
    bool CheckDomain( LPCSTR );  
    HRESULT ReadUserAccount();  
  
    //  
    //These constants define the common sizes of the   
    //  user account information throughout the program  
    //  
  
    const int USER_ACCOUNT_LEN = 256;  
    const int ACCOUNT_DOMAIN_LEN = 128;  
    ```  
  
5.  솔루션 탐색기에서 **소스 파일**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
6.  **새 항목 추가** 대화 상자에서 **C\+\+ 파일 \(.cpp\)**을 클릭합니다.  
  
7.  **이름** 상자에 **Bug.cpp**를 입력한 다음 **추가**를 클릭합니다.  
  
8.  다음 코드를 복사하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기에서 Bug.h 파일에 붙여넣습니다.  
  
    ```  
    #include <stdlib.h>  
    #include "Bug.h"  
  
    // the user account   
    TCHAR g_userAccount[USER_ACCOUNT_LEN] = "";  
    int len = 0;  
  
    bool ProcessDomain()  
    {  
        TCHAR* domain = new TCHAR[ACCOUNT_DOMAIN_LEN];  
        // ReadUserAccount gets a 'domain\user' input from   
        //the user into the global 'g_userAccount'  
        if (ReadUserAccount() )  
        {  
  
            // Copies part of the string prior to the '\'   
            // character onto the 'domain' buffer  
            for( len = 0 ; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != '\0') ; len++  )  
            {  
                if ( g_userAccount[len] == '\\' )   
                {  
                    // Stops copying on the domain and user separator ('\')   
                    break;  
                }  
                domain[len] = g_userAccount[len];          
            }  
            if((len= ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))  
            {  
                // '\' was not found. Invalid domain\user string.  
                delete [] domain;  
                return false;  
            }  
            else  
            {  
                domain[len]='\0';  
            }  
            // Process domain string  
            bool result = CheckDomain( domain );  
  
            delete[] domain;  
            return result;  
        }  
        return false;  
    }  
  
    int path_dependent(int n)  
    {  
        int i;  
        int j;  
        if (n == 0)  
            i = 1;  
        else  
            j = 1;  
        return i+j;   
    }  
    ```  
  
9. **파일** 메뉴를 클릭한 다음 **모두 저장**을 클릭합니다.  
  
### Annotations 프로젝트 추가 및 정적 라이브러리로 구성  
  
1.  솔루션 탐색기에서 **CppDemo**를 클릭하고 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트 추가** 대화 상자에서 Visual C\+\+를 확장하고 **일반**을 클릭한 다음 **빈 프로젝트**를 클릭합니다.  
  
3.  **이름** 텍스트 상자에 **Annotations**를 입력한 다음 **추가**를 클릭합니다.  
  
4.  솔루션 탐색기에서 **Annotations**를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
5.  **구성 속성**을 확장한 다음 **일반**을 클릭합니다.  
  
6.  **일반** 목록에서 **대상 확장명** 옆의 열에 있는 텍스트를 선택하고 **.lib**를 입력합니다.  
  
7.  **프로젝트 기본값**에서 **구성 형식** 옆의 열을 클릭하고 **정적 라이브러리 \(.lib\)**를 클릭합니다.  
  
### Annotations 프로젝트에 헤더 파일 및 소스 파일 추가  
  
1.  솔루션 탐색기에서 **Annotations**를 확장하고 **헤더 파일**을 마우스 오른쪽 단추로 클릭한 다음 **추가**를 클릭하고 **새 항목**을 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **헤더 파일 \(.h\)**을 클릭합니다.  
  
3.  **이름** 상자에 **annotations.h**를 입력한 다음 **추가**를 클릭합니다.  
  
4.  다음 코드를 복사하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기에서 **annotations.h** 파일에 붙여넣습니다.  
  
    ```  
    #include <CodeAnalysis/SourceAnnotations.h>  
  
    struct LinkedList  
    {  
        struct LinkedList* next;  
        int data;  
    };  
  
    typedef struct LinkedList LinkedList;  
  
    [returnvalue:SA_Post( Null=SA_Maybe )] LinkedList* AllocateNode();  
  
    ```  
  
5.  솔루션 탐색기에서 **소스 파일**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
6.  **새 항목 추가** 대화 상자에서 **코드**를 클릭한 다음 **C\+\+ 파일 \(.cpp\)**을 클릭합니다.  
  
7.  **이름** 상자에 **annotations.cpp**를 입력한 다음 **추가**를 클릭합니다.  
  
8.  다음 코드를 복사하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기에서 **annotations.cpp** 파일에 붙여넣습니다.  
  
    ```  
    #include <CodeAnalysis/SourceAnnotations.h>  
    #include <windows.h>  
    #include <stdlib.h>    
    #include "annotations.h"  
  
    LinkedList* AddTail( LinkedList *node, int value )  
    {  
        LinkedList *newNode = NULL;   
  
        // finds the last node  
        while ( node->next != NULL )   
        {  
            node = node->next;  
        }  
  
        // appends the new node  
        newNode = AllocateNode();   
        newNode->data = value;  
        newNode->next = 0;  
        node->next = newNode;  
  
        return newNode;  
    }  
  
    ```  
  
9. **파일** 메뉴를 클릭한 다음 **모두 저장**을 클릭합니다.