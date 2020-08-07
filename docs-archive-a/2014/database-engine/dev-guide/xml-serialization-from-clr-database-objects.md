---
title: Сериализация XML из объектов базы данных CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732974"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="d396f-102">Сериализация XML из объектов базы данных CLR</span><span class="sxs-lookup"><span data-stu-id="d396f-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="d396f-103">XML-сериализация используется в двух случаях:</span><span class="sxs-lookup"><span data-stu-id="d396f-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="d396f-104">при вызове веб-служб из объектов среды CLR;</span><span class="sxs-lookup"><span data-stu-id="d396f-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="d396f-105">для преобразования определяемого пользователем типа данных в XML.</span><span class="sxs-lookup"><span data-stu-id="d396f-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="d396f-106">Выполнение XML-сериализации с помощью вызова класса `XmlSerializer` обычно создает дополнительную сборку сериализации, перегружаемую в проект, содержащий исходную сборку. </span><span class="sxs-lookup"><span data-stu-id="d396f-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="d396f-107">Однако в целях безопасности в CLR эта перегрузка отключена.</span><span class="sxs-lookup"><span data-stu-id="d396f-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="d396f-108">Таким образом, чтобы вызвать веб-службу или выполнить преобразование из определяемого пользователем типа в XML внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , сборка должна быть создана вручную с помощью средства с именем **Sgen.exe** , предоставляемого .NET Framework, который создает необходимые сборки сериализации.</span><span class="sxs-lookup"><span data-stu-id="d396f-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="d396f-109">При вызове класса `XmlSerializer` следует создать сборку сериализации вручную, проделав следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="d396f-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="d396f-110">Запустите средство **Sgen.exe** , предоставляемое вместе с пакетом SDK для .NET Framework, чтобы создать сборку, содержащую сериализаторы XML для исходной сборки.</span><span class="sxs-lookup"><span data-stu-id="d396f-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="d396f-111">Зарегистрируйте созданную сборку в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью инструкции `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="d396f-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="d396f-112">Сведения об ошибках, которые могут быть получены при выполнении сериализации XML, см. в следующей служба поддержки Майкрософт статье ["не удается загрузить динамически созданную сборку сериализации"](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="d396f-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="d396f-113">Сведения о типах данных, не поддерживаемых классом XMLSerializer, см. в разделе о поддержке привязки к схеме XML на платформе .NET Framework в документации по платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d396f-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d396f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d396f-114">See Also</span></span>  
 <span data-ttu-id="d396f-115">[Доступ к данным из объектов базы данных CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d396f-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="d396f-116">CREATE ASSEMBLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d396f-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
