---
title: Procedimiento Obtener o establecer propiedades de situación de Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 9b280bf86f12b406582cb2f534edb85618515d76
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356330"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Filtrar Obtener o establecer propiedades de situación de Canvas
En este ejemplo se muestra cómo usar los métodos de posición el <xref:System.Windows.Controls.Canvas> elemento que se va a colocar el contenido secundario. Este ejemplo usa el contenido de un <xref:System.Windows.Controls.ListBoxItem> para representar valores de posición y convierte los valores en las instancias de <xref:System.Double>, que es un argumento necesario para el posicionamiento. Los valores, a continuación, se convierten en cadenas y se muestran como texto en un <xref:System.Windows.Controls.TextBlock> elemento utilizando el <xref:System.Windows.Controls.Canvas.GetLeft%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> elemento que tiene once seleccionable <xref:System.Windows.Controls.ListBoxItem> elementos. El <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> desencadenadores de eventos el `ChangeLeft` método personalizado, que define el bloque de código subsiguiente.  
  
 Cada <xref:System.Windows.Controls.ListBoxItem> representa un <xref:System.Double> valor, que es uno de los argumentos que el <xref:System.Windows.Controls.Canvas.SetLeft%2A> método <xref:System.Windows.Controls.Canvas> acepta. Para poder usar un <xref:System.Windows.Controls.ListBoxItem> para representar una instancia de <xref:System.Double>, primero debe convertir el <xref:System.Windows.Controls.ListBoxItem> al tipo de datos correcto.  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Cuando un usuario cambia el <xref:System.Windows.Controls.ListBox> selección, invoca el `ChangeLeft` método personalizado. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double> (tenga en cuenta que este valor ya se ha convertido en un <xref:System.String> utilizando el <xref:System.Windows.Controls.Control.ToString%2A> método). Este valor se pasa a continuación, volver a la <xref:System.Windows.Controls.Canvas.SetLeft%2A> y <xref:System.Windows.Controls.Canvas.GetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas> con el fin de cambiar la posición de la `text1` objeto.  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [Información general sobre elementos Panel](panels-overview.md)
