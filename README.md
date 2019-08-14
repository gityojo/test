```php:MTicketHistoryRepository.php
$data = DB::table('t_ticket_histories as t')
            ->join('m_backnumbers as b', 't.content_id', '=', 'b.backnumber_id')
            ->join('m_magazines as m', 'b.magazine_id', '=', 'm.id')
            ->select(DB::raw("DATE_FORMAT(used_at, '%Y/%m/%d') as used_date"), 'magazine_id', 'volume', 'content_id', 'episode_number', 'episode_title', 'used_at')
            ->orderBy('used_at')
            ->get();
```
