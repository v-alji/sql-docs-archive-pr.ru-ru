---
title: Документирование и создание скрипта для базы данных Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML for Analysis, scripts
- XMLA, scripts
- scripts [Analysis Services], databases
- documenting databases
- databases [Analysis Services], documenting
- databases [Analysis Services], scripts
ms.assetid: 125044e2-8d36-4733-8743-8bb68ff9aa4e
author: minewiskan
ms.author: owend
ms.openlocfilehash: cfe008b0d6903d7d012eb57d41d6e50240202ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667912"
---
# <a name="document-and-script-an-analysis-services-database"></a><span data-ttu-id="29b45-102">Документирование и работа со скриптами в базе данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="29b45-102">Document and Script an Analysis Services Database</span></span>
  <span data-ttu-id="29b45-103">После того как база данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] развернута, вы можете использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для вывода метаданных базы данных или объекта, содержащегося в ней, в качестве скрипта XML для аналитики (XMLA).</span><span class="sxs-lookup"><span data-stu-id="29b45-103">After an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script.</span></span> <span data-ttu-id="29b45-104">Можно вывести этот скрипт в новое окно **Редактор запросов XML для аналитики** , в файл или в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="29b45-104">You can output this script to a new **XMLA Query Editor** window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="29b45-105">Дополнительные сведения о XMLA см. в статье [Analysis Services языка сценариев &#40;языке ASSL&#41; справочнике](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="29b45-105">For more information about XMLA, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
 <span data-ttu-id="29b45-106">Сформированный скрипт XML для аналитики использует элементы языка скриптов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (ASSL) для определения объектов, содержащихся в скрипте.</span><span class="sxs-lookup"><span data-stu-id="29b45-106">The generated XMLA script uses [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) elements to define the objects contained by the script.</span></span> <span data-ttu-id="29b45-107">Если создан скрипт CREATE, результирующий скрипт XML для аналитики будет содержать команду XML для аналитики **Создать** и элементы ASSL, которые могут быть использованы для создания всей структуры базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="29b45-107">If you generated a CREATE script, the resulting XMLA script contains an XMLA **Create** command and ASSL elements that can be used to create the entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database structure on an instance.</span></span> <span data-ttu-id="29b45-108">Если создан скрипт ALTER, результирующий скрипт XML для аналитики будет содержать команду XML для аналитики **Изменить** и элементы ASSL, которые могут быть использованы для восстановления структуры существующей базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в состояние, в котором она находилась на момент создания скрипта.</span><span class="sxs-lookup"><span data-stu-id="29b45-108">If you generated an ALTER script, the resulting XMLA script contains an XMLA **Alter** command and ASSL elements that can be used to restore the structure of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database to the state of the database at the time the script was created.</span></span>  
  
 <span data-ttu-id="29b45-109">Созданный скрипт XML для аналитики из базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно использовать различными способами, в том числе:</span><span class="sxs-lookup"><span data-stu-id="29b45-109">You can use the generated XMLA script from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in many ways, including:</span></span>  
  
-   <span data-ttu-id="29b45-110">для поддержки скрипта резервного копирования, который позволяет повторно создавать разрешения и объекты базы данных;</span><span class="sxs-lookup"><span data-stu-id="29b45-110">To maintain a backup script that allows you to recreate all the database objects and permissions.</span></span>  
  
-   <span data-ttu-id="29b45-111">для создания или обновления кода разработки базы данных;</span><span class="sxs-lookup"><span data-stu-id="29b45-111">To create or update database development code.</span></span>  
  
-   <span data-ttu-id="29b45-112">для создания тестовой среды или среды разработки по существующей схеме.</span><span class="sxs-lookup"><span data-stu-id="29b45-112">To create a test or development environment from an existing schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b45-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="29b45-113">See Also</span></span>  
 <span data-ttu-id="29b45-114">[Изменение или удаление базы данных Analysis Services](modify-or-delete-an-analysis-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="29b45-114">[Modify or Delete an Analysis Services Database](modify-or-delete-an-analysis-services-database.md) </span></span>  
 <span data-ttu-id="29b45-115">[Элемент ALTER &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="29b45-115">[Alter Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span></span>  
 [<span data-ttu-id="29b45-116">Элемент Create (XMLA)</span><span class="sxs-lookup"><span data-stu-id="29b45-116">Create Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)  
  
  
