---
title: Доступ к пользовательским сборкам с использованием выражений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654055"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="25bcc-102">Доступ к пользовательским сборкам посредством выражений</span><span class="sxs-lookup"><span data-stu-id="25bcc-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="25bcc-103">После того как пользовательская сборка была создана, сделана доступной для конструктора отчетов или сервера отчетов, добавлена к подходящей политике безопасности, а также после того, как в определение отчета была добавлена ссылка на данную пользовательскую сборку, появится возможность доступа к членам классов сборки посредством выражений отчетов.</span><span class="sxs-lookup"><span data-stu-id="25bcc-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="25bcc-104">Для ссылки в выражении на пользовательский код следует вызвать элемент класса этой сборки.</span><span class="sxs-lookup"><span data-stu-id="25bcc-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="25bcc-105">Способ создания ссылки зависит от того, является ли метод статическим или основывается на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="25bcc-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="25bcc-106">Вызов статических членов из файла определения отчета</span><span class="sxs-lookup"><span data-stu-id="25bcc-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="25bcc-107">Статические члены принадлежат классу или типу, а не к созданному объекту.</span><span class="sxs-lookup"><span data-stu-id="25bcc-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="25bcc-108">Доступ к данным членам можно получить, напрямую вызвав их из класса. </span><span class="sxs-lookup"><span data-stu-id="25bcc-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="25bcc-109">По возможности для вызова пользовательских функций в отчете следует использовать статические члены, поскольку они обладают большей производительностью.</span><span class="sxs-lookup"><span data-stu-id="25bcc-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="25bcc-110">Для вызова статического члена необходимо сослаться на него как на выражение, принимающее вид =*Namespace.Class.Method*.</span><span class="sxs-lookup"><span data-stu-id="25bcc-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="25bcc-111">Вызов статических членов</span><span class="sxs-lookup"><span data-stu-id="25bcc-111">To call static members</span></span>  
  
-   <span data-ttu-id="25bcc-112">Для вызова статического члена следует установить выражение равным полностью указанному имени члена, в которое включено пространство имен, имя класса и имя члена.</span><span class="sxs-lookup"><span data-stu-id="25bcc-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="25bcc-113">Следующий пример вызывает метод **ToGBP**, преобразующий значение поля **StandardCost** из долларов в фунты стерлингов и отображающий это в отчете.</span><span class="sxs-lookup"><span data-stu-id="25bcc-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="25bcc-114">Важные сведения о статических полях и свойствах</span><span class="sxs-lookup"><span data-stu-id="25bcc-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="25bcc-115">В данный момент все отчеты выполняются в одном и том же домене приложения.</span><span class="sxs-lookup"><span data-stu-id="25bcc-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="25bcc-116">Это означает, что те отчеты, в которых присутствуют пользовательские статические данные, предоставляют доступ к этим данным другим экземплярам того же отчета.</span><span class="sxs-lookup"><span data-stu-id="25bcc-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="25bcc-117">В связи с этим статические данные одного пользователя могут стать доступны всем пользователям, которые в данное время выполняют этот определенный отчет.</span><span class="sxs-lookup"><span data-stu-id="25bcc-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="25bcc-118">В связи с этим не рекомендуется использовать статические поля или свойства в пользовательских сборках или в элементе **Code**; вместо этого в отчетах следует использовать поля или свойства экземпляров.</span><span class="sxs-lookup"><span data-stu-id="25bcc-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="25bcc-119">Однако статические методы можно использовать, поскольку они не сохраняют состояния или данные.</span><span class="sxs-lookup"><span data-stu-id="25bcc-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="25bcc-120">Вызов членов экземпляров из файла определения отчета</span><span class="sxs-lookup"><span data-stu-id="25bcc-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="25bcc-121">Если в пользовательской сборке содержатся члены экземпляров, к которым нужно обращаться из определения отчета, то в отчет следует добавить имя экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="25bcc-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="25bcc-122">Имя экземпляра для класса можно добавить, использовав вкладку **Код** диалогового окна **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="25bcc-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="25bcc-123">Дополнительные сведения о добавлении экземпляров классов в отчет см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25bcc-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="25bcc-124">Чтобы вызвать статический член, необходимо сослаться на него как на выражение, принимающее форму = Code *. InstanceName. Method*.</span><span class="sxs-lookup"><span data-stu-id="25bcc-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="25bcc-125">Вызов членов экземпляра</span><span class="sxs-lookup"><span data-stu-id="25bcc-125">To call instance members</span></span>  
  
-   <span data-ttu-id="25bcc-126">Для вызова члена экземпляра пользовательской сборки необходимо создать ссылку на ключевое слово **Code**, за которым следует имя экземпляра и метод.</span><span class="sxs-lookup"><span data-stu-id="25bcc-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="25bcc-127">Следующий пример вызывает метод экземпляра **ToEUR**, преобразующий значение поля **StandardCost** из долларов в евро и отображающий это в отчете.</span><span class="sxs-lookup"><span data-stu-id="25bcc-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="25bcc-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="25bcc-128">See Also</span></span>  
 [<span data-ttu-id="25bcc-129">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="25bcc-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
