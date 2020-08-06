---
title: Развертывание решений модели с помощью XMLA | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML scripts [Analysis Services]
- scripts [Analysis Services], deployment
- deploying [Analysis Services], XML scripts
- Analysis Services deployments, XML scripts
ms.assetid: a8cb1837-fcac-4730-bea4-a72cf94d9f7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b78490c5ab6ad3ba5e52bb82d4be254e3f5f102b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750303"
---
# <a name="deploy-model-solutions-using-xmla"></a><span data-ttu-id="5bb33-102">Развертывание решений модели с помощью XMLA</span><span class="sxs-lookup"><span data-stu-id="5bb33-102">Deploy Model Solutions Using XMLA</span></span>
  <span data-ttu-id="5bb33-103">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]параметр **Используя CREATE** команды **Создать скрипт для базы данных** создает XML-скрипт всей базы данных служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или одного из составляющих ее объектов.</span><span class="sxs-lookup"><span data-stu-id="5bb33-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an entire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or one of its constituent objects.</span></span> <span data-ttu-id="5bb33-104">Получившийся в результате скрипт затем можно запускать на другом компьютере для повторного создания схемы (метаданных) базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bb33-104">The resulting script can then be run on another computer to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="5bb33-105">Скрипт формирует всю базу данных, а механизм добавочного обновления уже развернутых объектов при использовании скрипта отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5bb33-105">The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script.</span></span> <span data-ttu-id="5bb33-106">После выполнения скрипта и развертывания базы данных вновь созданную базу необходимо обработать до ее просмотра пользователями.</span><span class="sxs-lookup"><span data-stu-id="5bb33-106">After running the script and deploying the database, the newly created database must be processed before users can browse it.</span></span>  
  
 <span data-ttu-id="5bb33-107">Дополнительные сведения о команде **Создать скрипт для базы данных** см. в разделе [Документирование и работа со скриптами в базе данных служб Analysis Services](document-and-script-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="5bb33-107">For more information about the **Script Database As** command, see [Document and Script an Analysis Services Database](document-and-script-an-analysis-services-database.md).</span></span>  
  
## <a name="modifying-object-properties-in-the-xml-script"></a><span data-ttu-id="5bb33-108">Изменение свойств объектов в XML-скрипте</span><span class="sxs-lookup"><span data-stu-id="5bb33-108">Modifying Object Properties in the XML Script</span></span>  
 <span data-ttu-id="5bb33-109">При использовании команды **Создать скрипт для базы данных** нельзя изменять определенные свойства (например, имя базы данных, строки соединений с источниками данных и параметры безопасности) объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="5bb33-109">When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects.</span></span> <span data-ttu-id="5bb33-110">Эти свойства необходимо либо изменить вручную в скрипте после его формирования, либо изменить в развернутой базе данных после выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="5bb33-110">These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5bb33-111">XML-скрипт не будет содержать пароль, если он указан в строке соединения для источника данных или для олицетворения.</span><span class="sxs-lookup"><span data-stu-id="5bb33-111">The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes.</span></span> <span data-ttu-id="5bb33-112">Поскольку в данном скрипте пароль требуется для обработки, его нужно добавить вручную в скрипт перед запуском либо добавить в XML после выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="5bb33-112">Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb33-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="5bb33-113">See Also</span></span>  
 <span data-ttu-id="5bb33-114">[Развертывание решений модели с помощью мастера развертывания](deploy-model-solutions-using-the-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5bb33-114">[Deploy Model Solutions Using the Deployment Wizard](deploy-model-solutions-using-the-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="5bb33-115">Синхронизация баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5bb33-115">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)  
  
  
