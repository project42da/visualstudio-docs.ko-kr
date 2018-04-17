---
title: 데이터베이스의 그림에 컨트롤 바인딩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 29d902f16051bd04079115baf87e33ac49d77396
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="bind-controls-to-pictures-from-a-database"></a>데이터베이스의 그림에 컨트롤 바인딩
사용할 수는 **데이터 소스** 창 응용 프로그램에서 컨트롤을 데이터베이스에 이미지를 바인딩할 수 있습니다. 예를 들어 이미지를 바인딩할 수 있습니다는 <xref:System.Windows.Controls.Image> WPF 응용 프로그램에서 또는 제어는 <xref:System.Windows.Forms.PictureBox> Windows Forms 응용 프로그램에서 제어 합니다.  
  
일반적으로 데이터베이스의 그림 바이트 배열로 저장 됩니다. 항목에 **데이터 원본** 로 설정 된 바이트 배열을 입력 제어로 저장 되어 있는 창 **None** 기본적으로 바이트 배열은 단순한 실행 파일에는 바이트의 배열에서 아무 것도 포함 될 수 있으므로 큰 응용 프로그램입니다. 바이트 배열 항목에 대 한 데이터 바인딩된 컨트롤을 만들려면는 **데이터 소스** 이미지를 나타내는 창을 만들 컨트롤을 선택 해야 합니다.  
  
다음 절차를 가정 하는 **데이터 소스** 창 이미지에 바인딩되는 항목으로 채워집니다. 
  
### <a name="to-bind-a-picture-in-a-database-to-a-control"></a>컨트롤에 데이터베이스에 그림을 바인딩하려면  
  
1.  디자인 화면에 컨트롤을 추가 하려면이 WPF 디자이너 또는 Windows Forms 디자이너에서 열려 있는지 확인 합니다.  
  
2.  에 **데이터 소스** 창 원하는 테이블을 확장 하거나 개체의 열 이나 속성을 표시 합니다.  
  
3.  열 이나 이미지 데이터를 포함 하는 속성을 선택 하 고 해당 드롭다운 컨트롤 목록에서 다음 컨트롤 중 하나를 선택 합니다.  
  
    -   WPF 디자이너를 연 경우 선택 **이미지**합니다.  
  
    -   Windows Forms 디자이너를 연 경우 선택 **PictureBox**합니다.  
  
    -   또는 데이터 바인딩을 지원 하 고 이미지를 표시할 수 있는 다른 컨트롤을 선택할 수 있습니다. 컨트롤을 사용 하려면 사용 가능한 컨트롤 목록에 없는 경우 목록에 추가 하 고 선택 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
## <a name="see-also"></a>참고자료
[Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)