---
title: Сжатие резервных копий (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655788"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="9138f-102">Сжатие резервных копий (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9138f-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="9138f-103">В этом разделе описывается сжатие резервных копий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в том числе ограничения, влияние сжатия резервных копий на производительность, настройка конфигурации сжатия резервных копий и коэффициент сжатия.</span><span class="sxs-lookup"><span data-stu-id="9138f-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9138f-104">Сведения о том, какие выпуски [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] поддерживают сжатие резервных копий, см. [в разделе функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="9138f-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="9138f-105">Сжатую резервную копию можно восстановить в любом выпуске [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9138f-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="9138f-106">Преимущества</span><span class="sxs-lookup"><span data-stu-id="9138f-106">Benefits</span></span>  
  
-   <span data-ttu-id="9138f-107">Так как сжатая резервная копия занимает меньше места, чем распакованная резервная копия тех же данных, для сжатия резервной копии обычно требуется меньше операций ввода-вывода какого-либо устройства, что обычно существенно повышает скорость резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9138f-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="9138f-108">Дополнительные сведения см. ниже в подразделе [Воздействие сжатых резервных копий на производительность](#PerfImpact).</span><span class="sxs-lookup"><span data-stu-id="9138f-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9138f-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9138f-109">Restrictions</span></span>  
 <span data-ttu-id="9138f-110">К сжатым резервным копиям применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="9138f-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="9138f-111">В наборе носителей не допускается одновременное существование сжатых и несжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="9138f-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="9138f-112">В предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] считывание сжатых резервных копий не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9138f-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="9138f-113">Резервные копии NT не могут совместно использовать магнитные ленты со сжатыми резервными копиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9138f-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="9138f-114">Воздействие сжатых резервных копий на производительность</span><span class="sxs-lookup"><span data-stu-id="9138f-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="9138f-115">По умолчанию сжатие существенно повышает загрузку ЦП. Дополнительная нагрузка на ЦП может помешать выполнению других операций.</span><span class="sxs-lookup"><span data-stu-id="9138f-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="9138f-116">Поэтому может потребоваться создать сжатые резервные копии с низким приоритетом в сеансе, для которого использование ЦП ограничивается[регулятором ресурсов](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="9138f-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="9138f-117">Дополнительные сведения см. ниже в подразделе [Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9138f-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="9138f-118">В целях оптимизации производительности операций ввода-вывода резервной копии их можно изолировать от устройств или закрепить за устройствами в зависимости от оценки следующих видов счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="9138f-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="9138f-119">Счетчики производительности операций ввода-вывода Windows, такие как счетчики физического использования дисков.</span><span class="sxs-lookup"><span data-stu-id="9138f-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="9138f-120">Счетчик **Пропускная способность устройства, байт/с** объекта [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="9138f-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="9138f-121">Счетчик **Пропускная способность резервного копирования и восстановления/с** объекта [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="9138f-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="9138f-122">Сведения о счетчиках Windows см. в справке Windows.</span><span class="sxs-lookup"><span data-stu-id="9138f-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="9138f-123">Сведения о работе со счетчиками SQL Server см. в разделе [Использование объектов SQL Server](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="9138f-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="9138f-124">Вычисление коэффициента сжатия для сжатой резервной копии</span><span class="sxs-lookup"><span data-stu-id="9138f-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="9138f-125">Чтобы вычислить коэффициент сжатия резервной копии, используйте значения столбцов **backup_size** и **compressed_backup_size** из таблицы журнала [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) для резервной копии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9138f-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="9138f-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="9138f-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="9138f-127">Например, коэффициент сжатия 3:1 обозначает, что экономится около 66% места на диске.</span><span class="sxs-lookup"><span data-stu-id="9138f-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="9138f-128">Чтобы запросить эти столбцы, можно выполнить следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="9138f-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="9138f-129">Коэффициент сжатия уже сжатой резервной копии зависит от подвергаемых сжатию данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="9138f-130">На полученный коэффициент сжатия оказывают влияние различные факторы.</span><span class="sxs-lookup"><span data-stu-id="9138f-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="9138f-131">К основным факторам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="9138f-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="9138f-132">Тип данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-132">The type of data.</span></span>  
  
     <span data-ttu-id="9138f-133">Символьные данные можно сжать сильнее, чем другие типы данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="9138f-134">Согласованность данных в строках на странице.</span><span class="sxs-lookup"><span data-stu-id="9138f-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="9138f-135">Как правило, если несколько строк на странице содержат одно и то же значение в каком-либо поле, для этого значения можно добиться существенного сжатия.</span><span class="sxs-lookup"><span data-stu-id="9138f-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="9138f-136">И наоборот, в базах данных, содержащих случайные значения или одну большую строку на странице, сжатые резервные копии будут практически такого же размера, что и несжатые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="9138f-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="9138f-137">Шифрование данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="9138f-138">Зашифрованные данные подвергаются сжатию в значительно меньшей степени, чем незашифрованные.</span><span class="sxs-lookup"><span data-stu-id="9138f-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="9138f-139">Если для шифрования всей базы данных используется прозрачное шифрование данных, сжатие резервных копий, возможно, ненамного снизит их размер, если снизит вообще.</span><span class="sxs-lookup"><span data-stu-id="9138f-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="9138f-140">Сжатие базы данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="9138f-141">Если база данных уже сжата, сжатие резервных копий может лишь незначительно сократить размер или не сократить его вообще.</span><span class="sxs-lookup"><span data-stu-id="9138f-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="9138f-142">Выделение пространства для файла резервной копии</span><span class="sxs-lookup"><span data-stu-id="9138f-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="9138f-143">При резервном копировании со сжатием конечный размер файла резервной копии зависит от степени сжимаемости исходных данных, которая становится известной только после окончания операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9138f-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="9138f-144">Вследствие этого изначальный размер файла резервной копии, создаваемого компонентом Database Engine при резервном копировании базы данных со сжатием, определяется с помощью алгоритма предварительного выделения.</span><span class="sxs-lookup"><span data-stu-id="9138f-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="9138f-145">Согласно данному алгоритму, размер создаваемого файла резервной копии соответствует стандартному проценту от размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="9138f-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="9138f-146">Если для операции резервного копирования необходимо больше пространства, компонент Database Engine увеличивает размер файла.</span><span class="sxs-lookup"><span data-stu-id="9138f-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="9138f-147">Если конечный размер меньше выделенного пространства, в конце операции резервного копирования компонент Database Engine сжимает файл до фактического конечного размера резервной копии.</span><span class="sxs-lookup"><span data-stu-id="9138f-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="9138f-148">Флаг трассировки 3042 позволяет создать файл резервной копии минимального размера, с последующим увеличением при необходимости до конечного размера.</span><span class="sxs-lookup"><span data-stu-id="9138f-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="9138f-149">При использовании флага трассировки 3042 операция резервного копирования не задействует алгоритм предварительного выделения пространства для резервной копии со сжатием.</span><span class="sxs-lookup"><span data-stu-id="9138f-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="9138f-150">Этот флаг трассировки полезен для экономии пространства, так как выделяется только фактическое пространство, необходимое для резервной копии со сжатием.</span><span class="sxs-lookup"><span data-stu-id="9138f-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="9138f-151">Однако, при использовании данного флага трассировки возможно небольшое уменьшение производительности (увеличение продолжительности операции резервного копирования).</span><span class="sxs-lookup"><span data-stu-id="9138f-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9138f-152">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9138f-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9138f-153">Настройка сжатия резервных копий (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9138f-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="9138f-154">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="9138f-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="9138f-155">Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9138f-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="9138f-156">DBCC TRACEON (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9138f-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="9138f-157">DBCC TRACEOFF (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9138f-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="9138f-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="9138f-158">See Also</span></span>  
 <span data-ttu-id="9138f-159">[Общие сведения о резервном копировании (SQL Server)](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9138f-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="9138f-160">Флаги трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9138f-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
