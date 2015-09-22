# laravel activitylogs 系统日志
#初始化
<pre>composer require xiuchanghu/activitylogs 1.0.0
文件config/app.php
providers数组增加
'Xiuchanghu\ActivityLogs\ActivityLogsServiceProvider',
aliases下增加
'Activity' => 'Xiuchanghu\ActivityLogs\Models\Activity',
php artisan migrate --path=vendor/xiuchanghu/activitylogs/src/migrations
php artisan vendor:publish
</pre>
#使用
<pre>Activity::log([
    'contentId'   => $user->id,
    'contentType' => 'User',
    'action'      => 'Create',
    'description' => '建立用户',
    'details'     => 'Username: '.$user->username,
]);
</pre>
