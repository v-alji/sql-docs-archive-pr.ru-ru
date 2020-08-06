---
title: Задание максимального размера для файла трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735721"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="651bd-102">установить максимальный размер для файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="651bd-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="651bd-103">Для указания максимального размера файла трассировки предусмотрена следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="651bd-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="651bd-104">Указание максимального размера файла трассировки</span><span class="sxs-lookup"><span data-stu-id="651bd-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="651bd-105">В меню **Файл** выберите команду **Создать трассировку**и подключитесь к экземпляру Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="651bd-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="651bd-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="651bd-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="651bd-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="651bd-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="651bd-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="651bd-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="651bd-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="651bd-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="651bd-110">В списке **Имя шаблона**выберите шаблон трассировки.</span><span class="sxs-lookup"><span data-stu-id="651bd-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="651bd-111">Выберите **Сохранить в файл**и укажите файл, в который будут сохранены данные о трассировке.</span><span class="sxs-lookup"><span data-stu-id="651bd-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="651bd-112">В поле **Установить максимальный размер файла** укажите максимальный размер файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="651bd-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="651bd-113">Когда файл достигает максимального размера, события трассировки перестают туда записываться.</span><span class="sxs-lookup"><span data-stu-id="651bd-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="651bd-114">Если выбран параметр **Включить операцию переключения на файл продолжения** (выбран по умолчанию), то происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="651bd-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="651bd-115">Если выбран параметр «операция переключения на файл продолжения», то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] закрывает текущий файл, как только он достигнет максимального размера, а затем создает новый файл.</span><span class="sxs-lookup"><span data-stu-id="651bd-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="651bd-116">У каждого нового файла будет то же имя, что и у предыдущего, но к этому имени будет добавляться целое число, соответствующее порядковому номеру файла. Например, если первоначальный файл трассировки назывался filename_1.trc, то следующий будет filename_2.trc и т.д.</span><span class="sxs-lookup"><span data-stu-id="651bd-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="651bd-117">Если новому файлу продолжения назначено имя, которое уже используется существующим файлом, то существующий файл будет перезаписан, при условии, что он не является доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="651bd-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="651bd-118">Параметр «операция переключения на файл продолжения» устанавливается автоматически при сохранении данных трассировки в файл.</span><span class="sxs-lookup"><span data-stu-id="651bd-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="651bd-119">Если параметр «операция переключения на файл продолжения» включен, то трассировка будет продолжаться до тех пор, пока не будет остановлена другими средствами.</span><span class="sxs-lookup"><span data-stu-id="651bd-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="651bd-120">Чтобы трассировка останавливалась по достижении максимального размера файла, отключите параметр «операция переключения на файл продолжения».</span><span class="sxs-lookup"><span data-stu-id="651bd-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="651bd-121">В файловой системе FAT32 максимально допустимый размер файла немногим меньше 4 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="651bd-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="651bd-122">Если файл трассировки достигает такого размера, то трассировка завершается с ошибкой «Недостаточно места на диске».</span><span class="sxs-lookup"><span data-stu-id="651bd-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="651bd-123">Чтобы можно было создавать файлы большего размера, используйте NTFS.</span><span class="sxs-lookup"><span data-stu-id="651bd-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651bd-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="651bd-124">See Also</span></span>  
 [<span data-ttu-id="651bd-125">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="651bd-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
