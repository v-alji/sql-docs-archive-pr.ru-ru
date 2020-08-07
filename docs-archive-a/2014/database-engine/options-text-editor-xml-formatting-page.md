---
title: Параметры (текстовый редактор — страница «форматирование XML») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732901"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="5c5fd-102">Параметры ("Текстовый редактор" — "XML" — страница "Форматирование")</span><span class="sxs-lookup"><span data-stu-id="5c5fd-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="5c5fd-103">При помощи этого диалогового окна можно задать настройки форматирования для XML-редактора.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="5c5fd-104">Диалоговое окно **Параметры** можно открыть из меню **Сервис**.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="5c5fd-105">Эти настройки доступны при выборе папки **Текстовый редактор**, папки **XML** и параметра **Форматирование** в диалоговом окне **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="5c5fd-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c5fd-106">Attributes</span></span>  
 <span data-ttu-id="5c5fd-107">**Сохранить ручное форматирование атрибутов**</span><span class="sxs-lookup"><span data-stu-id="5c5fd-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="5c5fd-108">Не переформатировать атрибуты.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-108">Do not reformat attributes.</span></span> <span data-ttu-id="5c5fd-109">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c5fd-110">Если атрибуты расположены на нескольких строках, редактор смещает каждую строку атрибутов, чтобы соответствовать структурированию родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="5c5fd-111">**Выравнивать атрибуты, чтобы каждый был на отдельной строке**</span><span class="sxs-lookup"><span data-stu-id="5c5fd-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="5c5fd-112">Расположить второй и последующий атрибуты вертикально, в соответствии со структурированием первого атрибута.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="5c5fd-113">Следующий XML-текст является примером расположения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="5c5fd-114">Автоматическое переформатирование</span><span class="sxs-lookup"><span data-stu-id="5c5fd-114">Auto Reformat</span></span>  
 <span data-ttu-id="5c5fd-115">**При вставке из буфера обмена**</span><span class="sxs-lookup"><span data-stu-id="5c5fd-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="5c5fd-116">Переформатировать XML-текст, вставленный из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="5c5fd-117">**По завершении закрывающего тега**</span><span class="sxs-lookup"><span data-stu-id="5c5fd-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="5c5fd-118">Переформатировать элемент по завершении закрывающего тега.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="5c5fd-119">Смешанное содержимое</span><span class="sxs-lookup"><span data-stu-id="5c5fd-119">Mixed Content</span></span>  
 <span data-ttu-id="5c5fd-120">**Форматировать смешанное содержимое по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="5c5fd-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="5c5fd-121">Произвести попытку переформатировать смешанное содержимое, за исключением тех случаев, когда содержание находится в области `xml:space="preserve"`.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="5c5fd-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-122">This is the default.</span></span>  
  
 <span data-ttu-id="5c5fd-123">Содержимое элемента считается смешанным, если он состоит из текста и разметки.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="5c5fd-124">Далее приводится пример элемента со смешанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="5c5fd-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="5c5fd-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c5fd-125">See Also</span></span>  
 [<span data-ttu-id="5c5fd-126">Редактор XML (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5c5fd-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
