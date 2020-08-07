---
title: 'Элемент &lt;xsd: redefine&gt; | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735130"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="d1068-102">Элемент &lt;xsd:redefine&gt;</span><span class="sxs-lookup"><span data-stu-id="d1068-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="d1068-103">Элемент W3C XSD **redefine** обеспечивает поддержку переопределения компонентов схемы.</span><span class="sxs-lookup"><span data-stu-id="d1068-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="d1068-104">Однако поддержка этой директивы является потенциально дорогостоящей для производительности, а также требует повторной [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверки всех экземпляров `xml` типа данных, связанных с переопределенной схемой.</span><span class="sxs-lookup"><span data-stu-id="d1068-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="d1068-105">Поэтому [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает этот элемент.</span><span class="sxs-lookup"><span data-stu-id="d1068-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="d1068-106">XML-схемы, которые включают элемент **\<xsd:redefine>** , будут отклонены сервером.</span><span class="sxs-lookup"><span data-stu-id="d1068-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="d1068-107">Чтобы обновить схему или ее компоненты, вместо этого можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="d1068-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="d1068-108">Создайте новую коллекцию XML-схем с измененными компонентами схемы.</span><span class="sxs-lookup"><span data-stu-id="d1068-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="d1068-109">Повторно введите все типы данных `xml` (XML DT), в которых используется переопределяемая коллекция схем XML, таким образом, чтобы в них использовалась новая коллекция.</span><span class="sxs-lookup"><span data-stu-id="d1068-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="d1068-110">Для повторного ввода столбцов воспользуйтесь параметром ALTER COLUMN команды ALTER TABLE или измените ограничения коллекции XML-схемы по переменным или параметрам.</span><span class="sxs-lookup"><span data-stu-id="d1068-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="d1068-111">Удалите старую версию коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="d1068-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1068-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1068-112">See Also</span></span>  
 [<span data-ttu-id="d1068-113">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="d1068-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
