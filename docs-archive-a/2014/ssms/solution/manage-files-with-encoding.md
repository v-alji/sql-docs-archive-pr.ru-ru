---
title: Управление файлами с помощью кодировок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669213"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="854b6-102">Управление файлами с помощью кодировок</span><span class="sxs-lookup"><span data-stu-id="854b6-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="854b6-103">Для отображения кода на конкретном языке и на конкретной платформе можно связать файл с определенной кодировкой.</span><span class="sxs-lookup"><span data-stu-id="854b6-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="854b6-104">Открытие файлов</span><span class="sxs-lookup"><span data-stu-id="854b6-104">Opening Files</span></span>  
 <span data-ttu-id="854b6-105">Можно выбрать редактор, используемый для изменения файла.</span><span class="sxs-lookup"><span data-stu-id="854b6-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="854b6-106">Открытие файла в определенном редакторе</span><span class="sxs-lookup"><span data-stu-id="854b6-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="854b6-107">В меню **Файл** наведите указатель мыши на пункт **Открыть**и выберите **Файл**.</span><span class="sxs-lookup"><span data-stu-id="854b6-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="854b6-108">В диалоговом окне **Открытие файла** выберите имя файла.</span><span class="sxs-lookup"><span data-stu-id="854b6-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="854b6-109">Нажмите стрелку рядом с кнопкой **Открыть** и в появившемся меню выберите пункт**Открыть с помощью** .</span><span class="sxs-lookup"><span data-stu-id="854b6-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="854b6-110">В списке **Выберите программу для открытия** выберите редактор и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="854b6-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="854b6-111">Чтобы открыть файл в определенной кодировке, выберите редактор с поддержкой кодировок, например редактор SQL-запросов с поддержкой кодировок или редактор XML с поддержкой кодировок.</span><span class="sxs-lookup"><span data-stu-id="854b6-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="854b6-112">Сохранение файлов</span><span class="sxs-lookup"><span data-stu-id="854b6-112">Saving Files</span></span>  
 <span data-ttu-id="854b6-113">Для поддержки различных языков можно также сохранять код с использованием Юникода или другой кодовой страницы, например западноевропейской или восточноевропейской.</span><span class="sxs-lookup"><span data-stu-id="854b6-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="854b6-114">Чтобы обеспечить отображение кода на определенном языке, можно связать файл с соответствующей кодировкой, а также определить символ конца строки для поддержки конкретной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="854b6-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="854b6-115">Кроме того, некоторые символы, использованные в именах файлов, не могут быть сохранены без использования кодировки Юникод.</span><span class="sxs-lookup"><span data-stu-id="854b6-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="854b6-116">Сохранение файла с другой кодировкой или символом конца строки</span><span class="sxs-lookup"><span data-stu-id="854b6-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="854b6-117">В меню **Файл** выберите команду **Сохранить \<filename> как**.</span><span class="sxs-lookup"><span data-stu-id="854b6-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="854b6-118">В диалоговом окне **Сохранение файла** раскройте кнопку **Сохранить** и выберите пункт **Выбор кодировки для сохранения**.</span><span class="sxs-lookup"><span data-stu-id="854b6-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="854b6-119">В диалоговом окне **Дополнительные параметры сохранения** выберите нужную кодировку из списка **Кодировка** .</span><span class="sxs-lookup"><span data-stu-id="854b6-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="854b6-120">В списке **Завершение строк**выберите нужный тип конца строки.</span><span class="sxs-lookup"><span data-stu-id="854b6-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="854b6-121">Если сохранить файл в кодировке Юникод, то этот файл следует возвращать в систему [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe как двоичный, поскольку Visual SourceSafe не поддерживает слияние, сравнение и отображение различий между файлами, сохраненными в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="854b6-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="854b6-122">При использовании Visual SourceSafe для хранения файлов в кодировках ANSI, UTF8 или Юникод следует учитывать ограничения, действующие для каждой из кодировок.</span><span class="sxs-lookup"><span data-stu-id="854b6-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="854b6-123">Для файлов в кодировке ANSI допускается использование только тех символов, которые поддерживаются в текущей кодовой странице, что ограничивает их международное использование.</span><span class="sxs-lookup"><span data-stu-id="854b6-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="854b6-124">Для файлов в кодировке Юникод не могут использоваться функции общего доступа для извлечения, проверки на наличие различий или слияния, поскольку они обрабатываются как двоичные.</span><span class="sxs-lookup"><span data-stu-id="854b6-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="854b6-125">Этот формат может использоваться в файлах, предназначенных для международного использования.</span><span class="sxs-lookup"><span data-stu-id="854b6-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="854b6-126">Файлы в кодировке UTF8 не могут надежно работать с Visual SourceSafe, поскольку при возврате, извлечении, проверке на наличие различий и слиянии производятся изменения, вызывающие проблемы при работе редакторов файлов UTF8.</span><span class="sxs-lookup"><span data-stu-id="854b6-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854b6-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="854b6-127">See Also</span></span>  
 <span data-ttu-id="854b6-128">[Файлы, управляющие решениями и проектами](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="854b6-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="854b6-129">Связывание расширения файла с редактором кода</span><span class="sxs-lookup"><span data-stu-id="854b6-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
