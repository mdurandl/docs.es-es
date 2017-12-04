---
title: Sobrecarga de operadores (F#)
description: "Obtenga información acerca de cómo sobrecargar los operadores aritméticos en una clase o tipo de registro y en el nivel global en F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 019277ed-f649-4fa5-ad43-097865f449d9
ms.openlocfilehash: 76ddab5339e11d71bb326b60d727017eb838ccf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="operator-overloading"></a><span data-ttu-id="f0930-104">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="f0930-104">Operator Overloading</span></span>

<span data-ttu-id="f0930-105">En este tema se describe cómo sobrecargar los operadores aritméticos de un tipo de clase o registro, así como en el nivel global.</span><span class="sxs-lookup"><span data-stu-id="f0930-105">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="f0930-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0930-106">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="f0930-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0930-107">Remarks</span></span>
<span data-ttu-id="f0930-108">En la sintaxis anterior, el *símbolo del operador* es uno de los `+`, `-`, `*`, `/`, `=`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f0930-108">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="f0930-109">El *lista de parámetros* especifica los operandos en el orden que aparecen en la sintaxis habitual para ese operador.</span><span class="sxs-lookup"><span data-stu-id="f0930-109">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="f0930-110">El *cuerpo del método* construye el valor resultante.</span><span class="sxs-lookup"><span data-stu-id="f0930-110">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="f0930-111">Las sobrecargas de operador para los operadores deben ser estáticas.</span><span class="sxs-lookup"><span data-stu-id="f0930-111">Operator overloads for operators must be static.</span></span> <span data-ttu-id="f0930-112">Las sobrecargas de operador para los operadores unarios, como `+` y `-`, debe utilizar una tilde (`~`) en el *símbolo del operador* para indicar que el operador es un operador unario y no es un operador binario, tal y como se muestra en el declaración siguiente.</span><span class="sxs-lookup"><span data-stu-id="f0930-112">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="f0930-113">En el código siguiente se muestra una clase vectorial que solo tiene dos operadores, uno para el unario menos y uno para la multiplicación por un escalar.</span><span class="sxs-lookup"><span data-stu-id="f0930-113">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="f0930-114">En el ejemplo, se necesitan dos sobrecargas para la multiplicación escalar porque el operador debe funcionar con independencia del orden en que aparezcan el vector y el escalar.</span><span class="sxs-lookup"><span data-stu-id="f0930-114">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="f0930-115">Crear operadores nuevos</span><span class="sxs-lookup"><span data-stu-id="f0930-115">Creating New Operators</span></span>
<span data-ttu-id="f0930-116">Se pueden sobrecargar todos los operadores estándar, pero también se pueden crear otros nuevos mediante secuencias de determinados caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0930-116">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="f0930-117">Permitidos son caracteres de operador `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, y `~`.</span><span class="sxs-lookup"><span data-stu-id="f0930-117">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="f0930-118">El carácter `~` tiene el significado especial de convertir en unario un operador y no forma parte de la secuencia de caracteres de operador.</span><span class="sxs-lookup"><span data-stu-id="f0930-118">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="f0930-119">Pueden convertir en no todos los operadores unarios.</span><span class="sxs-lookup"><span data-stu-id="f0930-119">Not all operators can be made unary.</span></span>

<span data-ttu-id="f0930-120">Según la secuencia de caracteres exacta utilizada, el operador tendrá una prioridad y una asociatividad determinadas.</span><span class="sxs-lookup"><span data-stu-id="f0930-120">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="f0930-121">La asociatividad puede ser de izquierda a derecha o de derecha a izquierda, y se utiliza siempre que aparecen en secuencia y sin paréntesis operadores que tienen el mismo nivel de prioridad.</span><span class="sxs-lookup"><span data-stu-id="f0930-121">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="f0930-122">El carácter operador `.` no afecta a la prioridad, de modo que, por ejemplo, para definir una versión propia de multiplicación que tenga la misma prioridad y asociatividad que la multiplicación ordinaria, se pueden crear operadores tales como `.*`.</span><span class="sxs-lookup"><span data-stu-id="f0930-122">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="f0930-123">Solo los operadores `?` y `?<-` puede empezar por `?`.</span><span class="sxs-lookup"><span data-stu-id="f0930-123">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="f0930-124">Se encuentra en una tabla que muestra la prioridad de todos los operadores en F # [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0930-124">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="f0930-125">Nombres de operador sobrecargados</span><span class="sxs-lookup"><span data-stu-id="f0930-125">Overloaded Operator Names</span></span>
<span data-ttu-id="f0930-126">Cuando el compilador de F# compila una expresión de operador, genera un método que tiene un nombre generado por compilador para ese operador.</span><span class="sxs-lookup"><span data-stu-id="f0930-126">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="f0930-127">Este es el nombre que aparece en el Lenguaje Intermedio de Microsoft (MSIL) para el método y también en reflexión e IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f0930-127">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="f0930-128">Normalmente, no es necesario utilizar estos nombres en el código de F#.</span><span class="sxs-lookup"><span data-stu-id="f0930-128">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="f0930-129">En la tabla siguiente se muestran los operadores estándar y sus nombres generados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f0930-129">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="f0930-130">Operador</span><span class="sxs-lookup"><span data-stu-id="f0930-130">Operator</span></span>|<span data-ttu-id="f0930-131">Nombre generado</span><span class="sxs-lookup"><span data-stu-id="f0930-131">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|
<span data-ttu-id="f0930-132">Hay otras combinaciones de caracteres de operador que no se muestran en este texto y que se pueden utilizar como operadores; sus nombres se crean a partir de la concatenación de los nombres de los caracteres individuales según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f0930-132">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="f0930-133">Por ejemplo, +!</span><span class="sxs-lookup"><span data-stu-id="f0930-133">For example, +!</span></span> <span data-ttu-id="f0930-134">se convierte en `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="f0930-134">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="f0930-135">Carácter de operador</span><span class="sxs-lookup"><span data-stu-id="f0930-135">Operator character</span></span>|<span data-ttu-id="f0930-136">Name</span><span class="sxs-lookup"><span data-stu-id="f0930-136">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="f0930-137">Operadores de prefijo e infijo</span><span class="sxs-lookup"><span data-stu-id="f0930-137">Prefix and Infix Operators</span></span>
<span data-ttu-id="f0930-138">*Prefijo* operadores se esperan que se coloquen delante de un operando o los operandos, como una función.</span><span class="sxs-lookup"><span data-stu-id="f0930-138">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="f0930-139">*Infijo* operadores se esperan que se coloquen entre los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="f0930-139">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="f0930-140">Solo se pueden usar determinados operadores como operadores de prefijo.</span><span class="sxs-lookup"><span data-stu-id="f0930-140">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="f0930-141">Algunos operadores siempre son operadores de prefijo, otros pueden ser de infijo o de prefijo, y el resto son siempre operadores de infijo.</span><span class="sxs-lookup"><span data-stu-id="f0930-141">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="f0930-142">Los operadores que comienzan por `!`, excepto `!=`, el operador `~` y las secuencias repetidas de `~`, son siempre operadores de prefijo.</span><span class="sxs-lookup"><span data-stu-id="f0930-142">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="f0930-143">Los operadores `+`, `-`, `+.`, `-.`, `&`, `&&`, `%` y `%%` pueden ser operadores de prefijo u operadores de infijo.</span><span class="sxs-lookup"><span data-stu-id="f0930-143">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="f0930-144">La versión prefija de estos operadores se distingue de su versión infija agregando `~` al principio de un operador de prefijo cuando se define.</span><span class="sxs-lookup"><span data-stu-id="f0930-144">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="f0930-145">`~` no se usa al utilizar el operador, solo al definirlo.</span><span class="sxs-lookup"><span data-stu-id="f0930-145">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="f0930-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0930-146">Example</span></span>

<span data-ttu-id="f0930-147">En el código siguiente se muestra el uso de la sobrecarga de operadores para implementar un tipo de fracción.</span><span class="sxs-lookup"><span data-stu-id="f0930-147">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="f0930-148">Una fracción se representa mediante un numerador y un denominador.</span><span class="sxs-lookup"><span data-stu-id="f0930-148">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="f0930-149">La función `hcf` se usa para determinar el factor común, que se utiliza para reducir fracciones.</span><span class="sxs-lookup"><span data-stu-id="f0930-149">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="f0930-150">**Salida:**</span><span class="sxs-lookup"><span data-stu-id="f0930-150">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="f0930-151">Operadores en el nivel global</span><span class="sxs-lookup"><span data-stu-id="f0930-151">Operators at the Global Level</span></span>
<span data-ttu-id="f0930-152">También se pueden definir operadores en el nivel global.</span><span class="sxs-lookup"><span data-stu-id="f0930-152">You can also define operators at the global level.</span></span> <span data-ttu-id="f0930-153">El código siguiente define un operador `+?`.</span><span class="sxs-lookup"><span data-stu-id="f0930-153">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="f0930-154">La salida del código anterior es `12`.</span><span class="sxs-lookup"><span data-stu-id="f0930-154">The output of the above code is `12`.</span></span>

<span data-ttu-id="f0930-155">De esta forma, es posible redefinir los operadores aritméticos normales porque las reglas de ámbito para F# dictan que los operadores recién definidos tienen prioridad respecto de los operadores integrados.</span><span class="sxs-lookup"><span data-stu-id="f0930-155">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="f0930-156">La palabra clave `inline` se suele utilizar con los operadores globales, que a menudo son pequeñas funciones que se integran mejor en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="f0930-156">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="f0930-157">Hacer que las funciones de operador sean inline permite que se puedan usar con los parámetros de tipo que se resuelven estáticamente a fin de generar código genérico resuelto estáticamente.</span><span class="sxs-lookup"><span data-stu-id="f0930-157">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="f0930-158">Para obtener más información, consulte [funciones Inline](functions/inline-functions.md) y [resuelto estáticamente los parámetros de tipo](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f0930-158">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0930-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0930-159">See Also</span></span>
[<span data-ttu-id="f0930-160">Miembros</span><span class="sxs-lookup"><span data-stu-id="f0930-160">Members</span></span>](members/index.md)