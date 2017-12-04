---
title: "ISymUnmanagedReader::GetDocumentVersion (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 377457fa852e1a4ae140f72d2dd83731490b81d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="b6c99-102">ISymUnmanagedReader::GetDocumentVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="b6c99-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="b6c99-103">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b6c99-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="b6c99-104">La versión del documento comienza en 1 y se incrementa cada vez que el documento se actualiza con la [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b6c99-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="b6c99-105">Si el `pbCurrent` parámetro es `true`, esta es la versión más reciente del documento.</span><span class="sxs-lookup"><span data-stu-id="b6c99-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c99-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6c99-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6c99-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6c99-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="b6c99-108">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b6c99-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="b6c99-109">[out] Un puntero a una variable que recibe la versión del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b6c99-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="b6c99-110">[out] Un puntero a una variable que recibe `true` si se trata de la versión más reciente del documento, o `false` si no se encuentra la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="b6c99-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6c99-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6c99-111">Return Value</span></span>  
 <span data-ttu-id="b6c99-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b6c99-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c99-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6c99-113">Requirements</span></span>  
 <span data-ttu-id="b6c99-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6c99-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c99-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6c99-115">See Also</span></span>  
 [<span data-ttu-id="b6c99-116">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6c99-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)