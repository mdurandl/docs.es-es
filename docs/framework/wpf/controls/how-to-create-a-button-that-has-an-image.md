---
title: Procedimiento Crear un botón que tenga una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352040"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Filtrar Crear un botón que tenga una imagen
En este ejemplo se muestra cómo incluir una imagen en un <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos <xref:System.Windows.Controls.Button> controles. Una <xref:System.Windows.Controls.Button> contiene texto y el otro contiene una imagen. La imagen está en una carpeta denominada datos, que es una subcarpeta de la carpeta del proyecto del ejemplo. Cuando un usuario hace clic en el <xref:System.Windows.Controls.Button> que tiene la imagen, el fondo y el texto de la otra <xref:System.Windows.Controls.Button> cambiar.  
  
 Este ejemplo se crea <xref:System.Windows.Controls.Button> controla mediante el uso de marcado, pero usa el código para escribir el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controladores de eventos.  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Vea también
- [Controles](index.md)
- [Biblioteca de controles](control-library.md)
