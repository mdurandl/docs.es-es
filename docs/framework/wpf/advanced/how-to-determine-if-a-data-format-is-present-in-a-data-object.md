---
title: Filtrar Determinar si un formato de datos está presente en un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 57190b94988c8ee557e99836a8e8500bfb622f2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379177"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a>Filtrar Determinar si un formato de datos está presente en un objeto de datos
Los ejemplos siguientes muestran cómo usar las distintas <xref:System.Windows.DataObject.GetDataPresent%2A> sobrecargas del método para consultar si un formato concreto está presente en un objeto de datos.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> sobrecarga para consultar la presencia de un formato concreto mediante la cadena de descriptor.  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> sobrecarga para consultar la presencia de un formato concreto por tipo.  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> sobrecarga para consultar los datos mediante la cadena de descriptor y especificar cómo tratar los formatos de datos.  
  
### <a name="code"></a>Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.IDataObject>
