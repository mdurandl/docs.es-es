---
title: "ICorDebugChain::GetCaller (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c714f321dc3c400b980d2d95b4655786fea9543b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="573c3-102">ICorDebugChain::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="573c3-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="573c3-103">Obtiene la cadena que ha llamado a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="573c3-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="573c3-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="573c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="573c3-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="573c3-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="573c3-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="573c3-107">Si esta cadena se llamó espontáneamente (como ocurriría si esta cadena o el depurador inicializara la pila de llamadas), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="573c3-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="573c3-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="573c3-108">Remarks</span></span>  
 <span data-ttu-id="573c3-109">La cadena de llamada puede estar en un subproceso diferente, si se calculan las referencias de la llamada entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="573c3-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573c3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="573c3-110">Requirements</span></span>  
 <span data-ttu-id="573c3-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="573c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="573c3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="573c3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="573c3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="573c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="573c3-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="573c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>