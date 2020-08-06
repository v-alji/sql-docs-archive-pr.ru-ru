---
title: Параметры (текстовый редактор — XML — страница "Разное") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 1a9509f0-c663-4b31-b396-7f5dc4371651
author: rothja
ms.author: jroth
ms.openlocfilehash: d937368d30122442ccbc40372a6b8e1cabc141e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727329"
---
# <a name="options-text-editor---xml---miscellaneous-page"></a><span data-ttu-id="70905-102">Параметры ("Текстовый редактор" — "XML" — страница "Разное")</span><span class="sxs-lookup"><span data-stu-id="70905-102">Options (Text Editor - XML - Miscellaneous Page)</span></span>

<span data-ttu-id="70905-103">Диалоговое окно **Параметры** позволяет изменять параметры автозаполнения и схемы для редактора XML.</span><span class="sxs-lookup"><span data-stu-id="70905-103">The **Options** dialog box lets you change the autocompletion and schema settings for the XML Editor.</span></span> <span data-ttu-id="70905-104">Для доступа к этим параметрам в меню **Сервис** щелкните пункт **Параметры**, разверните папку **Редактор текстов** , щелкните пункт **XML** , затем — пункт **Разное** .</span><span class="sxs-lookup"><span data-stu-id="70905-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, click **XML** and then click **Miscellaneous** .</span></span>  
  
## <a name="auto-insert"></a><span data-ttu-id="70905-105">Автоматическая вставка</span><span class="sxs-lookup"><span data-stu-id="70905-105">Auto Insert</span></span>  
 <span data-ttu-id="70905-106">**Закрывать теги**</span><span class="sxs-lookup"><span data-stu-id="70905-106">**Close tags**</span></span>  
 <span data-ttu-id="70905-107">Текстовый редактор добавляет завершающие теги при составлении элементов XML.</span><span class="sxs-lookup"><span data-stu-id="70905-107">The Text Editor adds close tags when authoring XML elements.</span></span> <span data-ttu-id="70905-108">Когда выбран начальный тег, редактор вставляет соответствующий завершающий тег, включая соответствующий префикс пространства имен.</span><span class="sxs-lookup"><span data-stu-id="70905-108">If an element start tag is selected, the editor inserts the matching close tag, including a matching namespace prefix.</span></span> <span data-ttu-id="70905-109">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-109">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="70905-110">**Кавычки атрибутов**</span><span class="sxs-lookup"><span data-stu-id="70905-110">**Attribute quotes**</span></span>  
 <span data-ttu-id="70905-111">При составлении XML-атрибутов редактор вставляет символы `="``"` и устанавливает курсор (**^)** внутри них.</span><span class="sxs-lookup"><span data-stu-id="70905-111">When authoring XML attributes, the editor inserts the `="``"` characters and positions the caret (**^)** inside the quotation marks.</span></span> <span data-ttu-id="70905-112">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-112">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="70905-113">**Объявления пространств имен**</span><span class="sxs-lookup"><span data-stu-id="70905-113">**Namespace declarations**</span></span>  
 <span data-ttu-id="70905-114">Редактор автоматически вставляет объявления пространств имен, где они необходимы.</span><span class="sxs-lookup"><span data-stu-id="70905-114">The editor automatically inserts namespace declarations wherever they are needed.</span></span> <span data-ttu-id="70905-115">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-115">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="70905-116">**Другая разметка (комментарии, CDATA)**</span><span class="sxs-lookup"><span data-stu-id="70905-116">**Other markup (Comments, CDATA)**</span></span>  
 <span data-ttu-id="70905-117">Комментарии, CDATA, DOCTYPE, инструкции обработки и другие элементы разметки завершаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="70905-117">Comments, CDATA, DOCTYPE, processing instructions, and other markup is autocompleted.</span></span> <span data-ttu-id="70905-118">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-118">This check box is selected by default.</span></span>  
  
## <a name="network"></a><span data-ttu-id="70905-119">Сеть</span><span class="sxs-lookup"><span data-stu-id="70905-119">Network</span></span>  
 <span data-ttu-id="70905-120">**Автоматически загружать DTD и схемы**</span><span class="sxs-lookup"><span data-stu-id="70905-120">**Automatically download DTDs and schemas**</span></span>  
 <span data-ttu-id="70905-121">Схемы и определения типов документов (DTD) автоматически загружаются с адресов HTTP.</span><span class="sxs-lookup"><span data-stu-id="70905-121">Schemas and document type definitions (DTDs) are automatically downloaded from HTTP locations.</span></span> <span data-ttu-id="70905-122">Эта функция использует System.Net в режиме автоматического определения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="70905-122">This feature uses System.Net with autoproxy server detection enabled.</span></span> <span data-ttu-id="70905-123">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-123">This check box is selected by default.</span></span>  
  
## <a name="outlining"></a><span data-ttu-id="70905-124">Структуризация</span><span class="sxs-lookup"><span data-stu-id="70905-124">Outlining</span></span>  
 <span data-ttu-id="70905-125">**Переходить в режим структурирования после открытия файлов**</span><span class="sxs-lookup"><span data-stu-id="70905-125">**Enter outlining mode when files open**</span></span>  
 <span data-ttu-id="70905-126">Включает функцию структурирования при открытии файла.</span><span class="sxs-lookup"><span data-stu-id="70905-126">Turns on the outlining feature when a file is opened.</span></span> <span data-ttu-id="70905-127">Этот флажок выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70905-127">This check box is selected by default.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="70905-128">Caching</span><span class="sxs-lookup"><span data-stu-id="70905-128">Caching</span></span>  
 <span data-ttu-id="70905-129">**Схемы**</span><span class="sxs-lookup"><span data-stu-id="70905-129">**Schemas**</span></span>  
 <span data-ttu-id="70905-130">Определяет местоположение кэша схемы.</span><span class="sxs-lookup"><span data-stu-id="70905-130">Specifies the location of the schema cache.</span></span> <span data-ttu-id="70905-131">Кнопка обзора (...) открывает текущее расположение кэша схемы в новом окне.</span><span class="sxs-lookup"><span data-stu-id="70905-131">The Browse button (...) opens the current schema cache location in a new window.</span></span> <span data-ttu-id="70905-132">Расположение по умолчанию — *\<Management Studio install directory>* \Xml\Schemas.</span><span class="sxs-lookup"><span data-stu-id="70905-132">The default location is *\<Management Studio install directory>* \Xml\Schemas.</span></span>  
