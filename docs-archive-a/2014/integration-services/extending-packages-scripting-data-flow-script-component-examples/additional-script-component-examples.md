---
title: Дополнительные примеры компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: 849dd38a-abb5-4702-a413-882aae3980a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 897ca075674f5c3dbaf355390fe8346580bf638a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665441"
---
# <a name="additional-script-component-examples"></a><span data-ttu-id="fe0a6-102">Дополнительные примеры компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="fe0a6-102">Additional Script Component Examples</span></span>
  <span data-ttu-id="fe0a6-103">Компонент скрипта является настраиваемым средством, которое можно использовать в потоке данных пакета, чтобы выполнить практическое любое требование, которое не удается выполнить с помощью источников, преобразований и назначений, входящих в состав служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe0a6-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="fe0a6-104">В этом разделе содержатся образцы кода компонента скрипта, демонстрирующие различные типы доступной функциональности.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-104">This section contains Script component code samples that demonstrate the various types of functionality that are available.</span></span>  
  
 <span data-ttu-id="fe0a6-105">Примеры, демонстрирующие настройку компонента скрипта как источника, преобразования или назначения, см. в разделе [Разработка компонентов скрипта определенных типов](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="fe0a6-105">For samples that demonstrate how to configure the Script component as a basic source, transformation, or destination, see [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe0a6-106">Если нужно создать компоненты, которые легко использовать повторно в нескольких задачах потока данных и нескольких пакетах, следует использовать код в приведенных образцах компонента скрипта в качестве начальной точки при создании компонентов пользовательского потока данных.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-106">If you want to create components that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in these Script component samples as the starting point for custom data flow components.</span></span> <span data-ttu-id="fe0a6-107">Дополнительные сведения см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fe0a6-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe0a6-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="fe0a6-108">In This Section</span></span>  
 [<span data-ttu-id="fe0a6-109">Имитация вывода ошибок для компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="fe0a6-109">Simulating an Error Output for the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md)  
 <span data-ttu-id="fe0a6-110">Компонент скрипта не поддерживает стандартный вывод ошибок, но его можно эмулировать с помощью небольшой дополнительной настройки и написания простого кода.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-110">The Script component does not support a standard error output, but you can simulate a standard error output with very little additional configuration and coding.</span></span>  
  
 [<span data-ttu-id="fe0a6-111">Расширение вывода ошибок с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="fe0a6-111">Enhancing an Error Output with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/enhancing-an-error-output-with-the-script-component.md)  
 <span data-ttu-id="fe0a6-112">Объясняет и демонстрирует добавление дополнительных сведений к стандартному выводу ошибок с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-112">Explains and demonstrates how to add additional information to a standard error output by using the Script component.</span></span>  
  
 [<span data-ttu-id="fe0a6-113">Создание назначения ODBC с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="fe0a6-113">Creating an ODBC Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/creating-an-odbc-destination-with-the-script-component.md)  
 <span data-ttu-id="fe0a6-114">Объясняет и демонстрирует создание назначения потока данных ODBC с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-114">Explains and demonstrates how to create an ODBC data flow destination by using the Script component.</span></span>  
  
 [<span data-ttu-id="fe0a6-115">Синтаксический анализ текстовых файлов нестандартного формата в компоненте скрипта</span><span class="sxs-lookup"><span data-stu-id="fe0a6-115">Parsing Non-Standard Text File Formats with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/parsing-non-standard-text-file-formats-with-the-script-component.md)  
 <span data-ttu-id="fe0a6-116">Объясняет и демонстрирует анализ двух разных нестандартных текстовых форматов в целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-116">Explains and demonstrates how to parse two different non-standard text file formats into destination tables.</span></span>  
  
<span data-ttu-id="fe0a6-117">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fe0a6-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fe0a6-118">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="fe0a6-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fe0a6-119">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="fe0a6-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fe0a6-120">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="fe0a6-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
