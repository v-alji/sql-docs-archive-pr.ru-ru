---
title: Обработка значений NULL (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665964"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="e2bad-102">Обработка значений NULL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e2bad-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="e2bad-103">Синтаксис XML определяет значение NULL как отсутствие.</span><span class="sxs-lookup"><span data-stu-id="e2bad-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="e2bad-104">(Например, если атрибут или элемент имеет значение NULL, этот атрибут или элемент отсутствует в XML-документе.) В [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML `updg:nullvalue` атрибут позволяет указать значение NULL для элемента или значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="e2bad-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="e2bad-105">Например, следующий диаграмма обновления гарантирует, что значение **заголовка** контакта со значением **ContactID** , равным 64, будет равно null, а затем обновите значение **заголовка** на «Mr».</span><span class="sxs-lookup"><span data-stu-id="e2bad-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="e2bad-106">для этого контакта.</span><span class="sxs-lookup"><span data-stu-id="e2bad-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e2bad-107">Когда параметры передаются диаграмме обновления, значение NULL может передаваться как значение параметра.</span><span class="sxs-lookup"><span data-stu-id="e2bad-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="e2bad-108">Это осуществляется путем указания атрибута `nullvalue` в блоке `<updg:header>`.</span><span class="sxs-lookup"><span data-stu-id="e2bad-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="e2bad-109">Пример см. в разделе [Передача параметров в диаграмм обновления &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e2bad-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bad-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2bad-110">See Also</span></span>  
 [<span data-ttu-id="e2bad-111">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e2bad-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
