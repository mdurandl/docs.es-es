---
title: "ICorDebugStackWalk::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 781998c9688dc60eec171068b50f432720ee0fdd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="d6002-102">ICorDebugStackWalk::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="d6002-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="d6002-103">Mueve el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto al marco siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6002-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6002-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6002-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d6002-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6002-105">Return Value</span></span>  
 <span data-ttu-id="d6002-106">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d6002-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d6002-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6002-107">HRESULT</span></span>|<span data-ttu-id="d6002-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6002-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6002-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6002-109">S_OK</span></span>|<span data-ttu-id="d6002-110">El tiempo de ejecución se desenreda correctamente al marco siguiente (vea comentarios).</span><span class="sxs-lookup"><span data-stu-id="d6002-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="d6002-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d6002-111">E_FAIL</span></span>|<span data-ttu-id="d6002-112">El `ICorDebugStackWalk` no se pudo avanzar el objeto.</span><span class="sxs-lookup"><span data-stu-id="d6002-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="d6002-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="d6002-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="d6002-114">Se alcanzó el final de la pila como resultado de este desenredo.</span><span class="sxs-lookup"><span data-stu-id="d6002-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="d6002-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="d6002-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="d6002-116">El puntero de marco ya está al final de la pila; por lo tanto, no puede tener acceso a ningún marco adicional.</span><span class="sxs-lookup"><span data-stu-id="d6002-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d6002-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="d6002-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6002-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6002-118">Remarks</span></span>  
 <span data-ttu-id="d6002-119">El `Next` método avanza el `ICorDebugStackWalk` objeto al marco de llamada solo si el runtime puede desenredar el marco actual.</span><span class="sxs-lookup"><span data-stu-id="d6002-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="d6002-120">En caso contrario, el objeto avanza al marco siguiente que el runtime puedo desenredar.</span><span class="sxs-lookup"><span data-stu-id="d6002-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6002-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6002-121">Requirements</span></span>  
 <span data-ttu-id="d6002-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6002-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6002-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6002-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6002-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6002-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6002-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6002-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6002-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6002-126">See Also</span></span>  
 [<span data-ttu-id="d6002-127">ICorDebugStackWalk (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6002-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="d6002-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6002-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d6002-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="d6002-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)