---
title: Propiedades (F#)
description: "Obtenga información sobre F # propiedades, que son miembros que representan valores asociados a un objeto."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a><span data-ttu-id="9342a-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9342a-104">Properties</span></span>

<span data-ttu-id="9342a-105">*Propiedades* son miembros que representan valores asociados a un objeto.</span><span class="sxs-lookup"><span data-stu-id="9342a-105">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="9342a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9342a-106">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="9342a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9342a-107">Remarks</span></span>
<span data-ttu-id="9342a-108">Las propiedades representan el "tiene un" relación en la programación orientada a objetos, que representa los datos que están asociados con instancias de objeto o, para las propiedades estáticas, con el tipo.</span><span class="sxs-lookup"><span data-stu-id="9342a-108">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="9342a-109">Puede declarar propiedades de dos maneras, dependiendo de si desea especificar explícitamente el valor subyacente (conocida también como el almacén de copias de seguridad de) para la propiedad, o si desea permitir que el compilador genere automáticamente el almacén de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9342a-109">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="9342a-110">Por lo general, debe usar la forma más explícita si la propiedad tiene una implementación no trivial y la forma automática cuando la propiedad es simplemente un contenedor simple para un valor o una variable.</span><span class="sxs-lookup"><span data-stu-id="9342a-110">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="9342a-111">Para declarar una propiedad de forma explícita, use la `member` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="9342a-111">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="9342a-112">Esta sintaxis declarativa va seguida de la sintaxis que especifica la `get` y `set` métodos, también denominadas *descriptores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="9342a-112">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="9342a-113">Las distintas formas de sintaxis explícita que se muestra en la sección de sintaxis se usan para las propiedades de lectura/escritura, de solo lectura y de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9342a-113">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="9342a-114">Para las propiedades de solo lectura, definir solo un `get` método; para las propiedades de solo escritura, definir solo un `set` método.</span><span class="sxs-lookup"><span data-stu-id="9342a-114">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="9342a-115">Tenga en cuenta que, cuando una propiedad tiene `get` y `set` descriptores de acceso, la sintaxis alternativa le permite especificar los atributos y modificadores de accesibilidad que son diferentes para cada descriptor de acceso, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9342a-115">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="9342a-116">Para propiedades de lectura/escritura, que tienen tanto un `get` y `set` /método siguiente, el orden de `get` y `set` se puede invertir.</span><span class="sxs-lookup"><span data-stu-id="9342a-116">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="9342a-117">Como alternativa, puede proporcionar la sintaxis mostrada para `get` solo y la sintaxis mostrada para `set` solo en lugar de usar la sintaxis combinada.</span><span class="sxs-lookup"><span data-stu-id="9342a-117">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="9342a-118">Esto resulta más fácil para comentar el individuo `get` o `set` método, si es algo que deba realizar.</span><span class="sxs-lookup"><span data-stu-id="9342a-118">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="9342a-119">Esta alternativa al uso de la sintaxis combinada se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9342a-119">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="9342a-120">Privada valores que espera los datos para las propiedades se denominan *memorias auxiliares*.</span><span class="sxs-lookup"><span data-stu-id="9342a-120">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="9342a-121">Para hacer que el compilador crea automáticamente el almacén de copia de seguridad, utilice las palabras clave `member val`, omitir el identificador automática, a continuación, proporcione una expresión para inicializar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-121">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="9342a-122">Si la propiedad es mutable, incluir `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="9342a-122">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="9342a-123">Por ejemplo, el siguiente tipo de clase incluye dos propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9342a-123">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="9342a-124">`Property1`es de solo lectura y se inicializa en el argumento proporcionado al constructor primario, y `Property2` es una propiedad configurable que se inicializa en una cadena vacía:</span><span class="sxs-lookup"><span data-stu-id="9342a-124">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="9342a-125">Propiedades implementadas automáticamente son parte de la inicialización de un tipo, por lo que deben incluirse antes de las definiciones de miembros, igual que `let` enlaces y `do` enlaces en una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="9342a-125">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="9342a-126">Tenga en cuenta que solo se evalúa la expresión que inicialice una propiedad implementada automáticamente en la inicialización y no cada vez que se tiene acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-126">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="9342a-127">Este comportamiento difiere del comportamiento de una propiedad implementada explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9342a-127">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="9342a-128">Lo que esto significa que es el código para inicializar estas propiedades se agrega al constructor de una clase.</span><span class="sxs-lookup"><span data-stu-id="9342a-128">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="9342a-129">Considere el siguiente código que muestra esta diferencia:</span><span class="sxs-lookup"><span data-stu-id="9342a-129">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="9342a-130">**Salida**</span><span class="sxs-lookup"><span data-stu-id="9342a-130">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="9342a-131">El resultado del código anterior muestra que el valor de AutoProperty no cambia cuando se llama varias veces, mientras que el ExplicitProperty cambia cada vez que se llama.</span><span class="sxs-lookup"><span data-stu-id="9342a-131">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="9342a-132">Esto demuestra que la expresión de una propiedad implementada automáticamente no se evalúa cada vez, como es el método de captador de propiedad explícitos.</span><span class="sxs-lookup"><span data-stu-id="9342a-132">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="9342a-133">Hay algunas bibliotecas, por ejemplo, Entity Framework (`System.Data.Entity`) que realizan operaciones personalizadas en los constructores de clase base que no funcionan bien con la inicialización de propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9342a-133">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="9342a-134">En esos casos, pruebe a usar propiedades explícitas.</span><span class="sxs-lookup"><span data-stu-id="9342a-134">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="9342a-135">Propiedades pueden ser miembros de clases, estructuras, uniones discriminadas, registros, interfaces y extensiones de tipo y también se pueden definir en expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="9342a-135">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="9342a-136">Atributos se pueden aplicar a propiedades.</span><span class="sxs-lookup"><span data-stu-id="9342a-136">Attributes can be applied to properties.</span></span> <span data-ttu-id="9342a-137">Para aplicar un atributo a una propiedad, escribir el atributo en una línea independiente antes de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-137">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="9342a-138">Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="9342a-138">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="9342a-139">De forma predeterminada, las propiedades son públicas.</span><span class="sxs-lookup"><span data-stu-id="9342a-139">By default, properties are public.</span></span> <span data-ttu-id="9342a-140">Modificadores de accesibilidad también puede aplicarse a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9342a-140">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="9342a-141">Para aplicar un modificador de accesibilidad, agregará inmediatamente antes del nombre de la propiedad si está diseñado para que se aplican a ambos el `get` y `set` métodos; agregarlo antes de la `get` y `set` palabras clave si es de distintos tipos de accesibilidad se requiere para cada descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="9342a-141">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="9342a-142">El *modificador de accesibilidad* puede ser uno de los siguientes: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="9342a-142">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="9342a-143">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="9342a-143">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="9342a-144">Las implementaciones de propiedad se ejecutan cada vez que se tiene acceso a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-144">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="9342a-145">Estáticos y propiedades de la instancia</span><span class="sxs-lookup"><span data-stu-id="9342a-145">Static and Instance Properties</span></span>
<span data-ttu-id="9342a-146">Propiedades pueden ser estáticos o propiedades de la instancia.</span><span class="sxs-lookup"><span data-stu-id="9342a-146">Properties can be static or instance properties.</span></span> <span data-ttu-id="9342a-147">Propiedades estáticas se pueden invocar sin una instancia y se usan para los valores asociados con el tipo, no a los objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="9342a-147">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="9342a-148">Para las propiedades estáticas, omitir el identificador automática.</span><span class="sxs-lookup"><span data-stu-id="9342a-148">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="9342a-149">Self-identifier es necesario para las propiedades de instancia.</span><span class="sxs-lookup"><span data-stu-id="9342a-149">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="9342a-150">La siguiente definición de propiedad estática se basa en un escenario en el que tiene un campo estático `myStaticValue` que es el almacén de respaldo para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-150">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="9342a-151">Las propiedades también pueden ser como una matriz, en cuyo caso se les llama *propiedades indizadas*.</span><span class="sxs-lookup"><span data-stu-id="9342a-151">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="9342a-152">Para obtener más información, consulte [propiedades indizadas](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9342a-152">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="9342a-153">Anotación de tipo para las propiedades</span><span class="sxs-lookup"><span data-stu-id="9342a-153">Type Annotation for Properties</span></span>
<span data-ttu-id="9342a-154">En muchos casos, el compilador tiene información suficiente para inferir el tipo de una propiedad del tipo de la memoria auxiliar, pero puede establecer explícitamente el tipo mediante la adición de una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="9342a-154">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="9342a-155">Usar propiedad conjunto de descriptores de acceso</span><span class="sxs-lookup"><span data-stu-id="9342a-155">Using Property set Accessors</span></span>
<span data-ttu-id="9342a-156">Puede establecer las propiedades que proporcionan `set` descriptores de acceso mediante el uso de la `<-` operador.</span><span class="sxs-lookup"><span data-stu-id="9342a-156">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="9342a-157">El resultado es **20**.</span><span class="sxs-lookup"><span data-stu-id="9342a-157">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="9342a-158">Propiedades abstractas</span><span class="sxs-lookup"><span data-stu-id="9342a-158">Abstract Properties</span></span>
<span data-ttu-id="9342a-159">Propiedades pueden ser abstractas.</span><span class="sxs-lookup"><span data-stu-id="9342a-159">Properties can be abstract.</span></span> <span data-ttu-id="9342a-160">Al igual que con los métodos, `abstract` simplemente significa que hay una distribución virtual asociada a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9342a-160">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="9342a-161">Propiedades abstractas pueden ser verdaderamente abstractas, es decir, sin una definición de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="9342a-161">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="9342a-162">Por lo tanto, la clase que contiene este tipo de propiedad es una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="9342a-162">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="9342a-163">Como alternativa, abstracta puede significar que una propiedad es virtual, y en ese caso, una definición debe estar presente en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="9342a-163">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="9342a-164">Tenga en cuenta que las propiedades abstractas no deben ser privadas, y si un descriptor de acceso es abstracto, el otro debe también ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="9342a-164">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="9342a-165">Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="9342a-165">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="9342a-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="9342a-166">See Also</span></span>
[<span data-ttu-id="9342a-167">Miembros</span><span class="sxs-lookup"><span data-stu-id="9342a-167">Members</span></span>](index.md)

[<span data-ttu-id="9342a-168">Métodos</span><span class="sxs-lookup"><span data-stu-id="9342a-168">Methods</span></span>](methods.md)