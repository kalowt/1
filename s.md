## version 0.2.17
#### release date: 2016-12-30

```sequence

participant A

participant B

participant C as C_Alias

```

### 1. classroom_activity 新增 bg_image 欄位
```mysql
ALTER TABLE  `classroom_activity` ADD  `bg_image` VARCHAR( 255 ) NOT NULL COMMENT  '活動背景圖' AFTER  `src_cover`
```

### 2. course 新增 first_publish 欄位
```mysql
ALTER TABLE  `course` ADD  `first_publish` tinyint(1) NOT NULL DEFAULT 1 COMMENT  '第一次上架' AFTER  `copy_course_id`
```

## version 0.2.16
#### release date: 2016-12-02

### 1. user 新增 org_name 欄位
```mysql
ALTER TABLE  `user` ADD  `org_name` varchar(255) NOT NULL AFTER `org_id`;
```

### 2. 增加課堂活動圖片上傳格式
```php
$config['classroom_activity_allowed_types'] = array('jpg', 'png', 'JPG', 'PNG');
```

## version 0.2.15
#### release date: 2016-10-28

### 1. 複製出config.php做為個別運行環境的設定文件
```
cp .../config.sample.php .../config.php
```

### 2. 新增 course_copy_progress table
```mysql
CREATE TABLE IF NOT EXISTS `course_copy_progress` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `course_id` int(11) NOT NULL,
  `user_id` int(11) NOT NULL,
  `state` text NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```

## version 0.2.14
#### release date: 2016-10-07

### 1. global.sample.php 新增 首頁判斷變數
```
//old, mess, makers
$config['homepage'] = "mess";
```

### 2. 新增 account_group table
```mysql
CREATE TABLE IF NOT EXISTS `account_group` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL,
  `user_id` int(11) NOT NULL,
  `admin` tinyint(4) NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```

### 3. 新增 account_group_user table
```mysql
CREATE TABLE IF NOT EXISTS `account_group_user` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `group_id` int(11) NOT NULL,
  `teach_id` int(11) NOT NULL,
  `student_id` int(11) NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```

## version 0.2.13
#### release date: 2016-09-30

### 1. 增加daily report的欄位內容
```mysql
ALTER TABLE `daily_report` CHANGE `type` `type` ENUM( 'user_register', 'user_register_append', 'user_register_guest', 'user_login_web', 'user_login_app', 'user_login_web_and_app', 'material_click', 'guest_material_click' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL COMMENT '單日註冊開通總人數, 單日附屬帳號數, 單日訪客數, 單日Web登入人數, 單日App登入人數, 單日Web和App都登入人數, 單日點擊素材人數, 單日不登入且點擊素材人數'
```

### 2. appendant_member_share 新增 is_group 欄位
```mysql
ALTER TABLE  `appendant_member_share` ADD  `is_group` tinyint(4) NOT NULL AFTER `teach_id`;
```

### 3. 更新app_version
```mysql
UPDATE `app_version` SET `version`='3.0.1',`update_address`='https://goo.gl/j00hsJ' WHERE `name` = 'classroom'
```

## version 0.2.12
#### release date: 2016-09-02

### 1. global.sample.php 新增 副本系統email
```
//system email
$config['systemail_from'] = "no-reply@dopod.com";
$config['systemail_cc'] = "service@dopod.com";
```

### 2. 課程新增 是否開放複製欄位
```mysql
ALTER TABLE  `course` ADD  `copy` TINYINT( 1 )  NOT NULL COMMENT  '是否開放複製' AFTER  `publish`
```

### 3. course_user 新增 ta (Teaching assistant) 角色
```mysql
ALTER TABLE  `course_user` CHANGE  `role`  `role` ENUM(  'teacher',  'student',  'ta' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL
```

### 4. app_version
#### 4.1 新增 update_address(更新檔網址)欄位
```mysql
ALTER TABLE `app_version` ADD `update_address` varchar(255) NOT NULL  COMMENT '更新檔網址' AFTER `version`;
```
#### 4.2 填入classroom, practice的更新檔網址
```
classroom: http://goo.gl/VmJkGh
practice:  http://goo.gl/1f2Ehv
```
#### 4.3 新增account manager版本資料
```mysql
INSERT INTO `app_version`(`name`, `version`, `update_address`) VALUES ('account_manager', '5.0.0', 'http://goo.gl/idNXcZ');
```

### 5. hyperlink 新增 publish 欄位
```mysql
ALTER TABLE `hyperlink` ADD `publish` TINYINT( 1 ) NOT NULL COMMENT '發佈,未發佈' AFTER `name`;
```

### 6. 補附屬帳號建立時間順序，請CD至目錄位置cd /var/www/lms/patch
```linux
  php account_duration.php
```

### 7. 重建question_template的search資料
```
將 `patch/search_add.php` 放在 `application/controllers`
修改 private $search_type = array('question_template');
修改 private $mysql_table = array('question_template');

執行連結 http://staging-lms.learnmode.net/search_add
執行連結 http://staging-lms.learnmode.net/search_add/patch
```

## version 0.2.11

### 1. 增加 teacher_review (教師審核) 資料表
```mysql
CREATE TABLE IF NOT EXISTS `teacher_review` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_id` int(11) NOT NULL,
  `contact_tel` varchar(255) NOT NULL,
  `service` varchar(255) NOT NULL,
  `certificate` varchar(255) NOT NULL,
  `content` text NOT NULL,
  `inspector` varchar(255) NOT NULL,
  `state` enum('pending','accepted','rejected','suspend') NOT NULL,
  `enterdate` datetime NOT NULL,
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```

### 2. add client_app_id and client_app_secret in global.php
```php
  $config['client_app_id'] = 'superclient_app';
  $config['client_app_secret'] = 'ad25df57e74bee7afd81994cc127f292338a6a54';
```

### 3. 課程資料表 增加三個欄位
```mysql
ALTER TABLE  `course` ADD  `share` TINYINT(4) NOT NULL COMMENT  '共享' AFTER  `recommend`
ALTER TABLE  `course` ADD  `share_rank` INT NOT NULL COMMENT  '首頁共享排序位置' AFTER  `home_rank`
ALTER TABLE  `course` ADD  `copy_course_id` INT NOT NULL COMMENT  '複製的父課程ID' AFTER  `price`
```

### 4. 新增附屬帳號表格
```mysql
  CREATE TABLE IF NOT EXISTS `appendant_admin_user` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `student_id` int(11) NOT NULL,
    `teach_id` int(11) NOT NULL,
    `admin` int(11) NOT NULL,
    `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
    PRIMARY KEY (`id`)
  ) ENGINE=MyISAM  DEFAULT CHARSET=utf8;

  CREATE TABLE IF NOT EXISTS `appendant_member_share` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `share_id` int(11) NOT NULL,
    `teach_id` int(11) NOT NULL,
    `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
    PRIMARY KEY (`id`)
  ) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```
### 5. 修改user表格的permission欄位和新增stud_pwd欄位
```mysql
ALTER TABLE  `user` CHANGE  `permission`  `permission` ENUM(  'admin', 'teacher', 'user', 'student', 'guest' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL COMMENT  '"admin": 總管理員, "teacher": 教師, "student": 學生, "guest": 訪客';
ALTER TABLE  `user` ADD  `stud_pwd` varchar(255) NOT NULL COMMENT  '學生密碼' AFTER  `password`;
```

### 6. 增加 teacher_review (教師審核) 資料表 欄位
```
ALTER TABLE  `teacher_review` ADD  `contact_phone` VARCHAR( 255 ) NOT NULL COMMENT  '行動電話' AFTER  `user_id`
```
### 7. 課程新增 課程代碼欄位
```mysql
ALTER TABLE  `course` ADD  `passcode` varchar(6) COMMENT  '課程通行碼' AFTER  `hash`;
```
### 8. add import_allowed_types in global.php
```php
  //virtual user import type
  $config['import_allowed_types'] = array('xlsx', 'xls');
```

## version 0.2.8~增加兩個欄位

### 1. 超連結表格增加兩個欄位
```mysql
  ALTER TABLE  `hyperlink` ADD  `name` varchar(255) NOT NULL AFTER `admin_id`;
  ALTER TABLE  `hyperlink` ADD  `description` text NOT NULL AFTER `name`;
```

### 2. add newbie_course_number in global.php
```php
  $config['newbie_course_number'] = '填入你的新手課程ID';
```

## version 0.2.7~

### 1. 課堂和影片資料表增加首頁顯示排序欄位
```mysql
  ALTER TABLE  `course` ADD  `home_rank` INT( 11 ) NOT NULL DEFAULT  '0' COMMENT  '首頁顯示排序位置' AFTER  `major`;
  ALTER TABLE  `video` ADD  `home_rank` INT( 11 ) NOT NULL DEFAULT  '0' COMMENT  '首頁顯示排序位置' AFTER  `recommend`;
```

### 2. add knowledge_root and Knowledge_version_root settings in global.php
```php
  $config['knowledge_root'] = 2;
  $config['knowledge_version_root'] = 25;
```

### 3. 增加 course_chapter 素材屬性
```mysql
  ALTER TABLE  `course_chapter` CHANGE  `res_type`  `res_type` ENUM(  'chapter',  'book',  'video',  'test',  'classroom',  'homework',  'audio',  'hyperlink' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL COMMENT  '素材類型'
```

### 4. 增加 hyperlink (超連結) 資料表
```mysql
CREATE TABLE `hyperlink` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `course_id` int(11) NOT NULL COMMENT '所屬課程',
  `admin_id` int(11) NOT NULL COMMENT '建立者',
  `url` varchar(255) NOT NULL,
  `browses` int(11) NOT NULL COMMENT '瀏覽人數',
  `views` int(11) NOT NULL COMMENT '觀看人數',
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  `deleted` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `course_id` (`course_id`)
) ENGINE=MyISAM AUTO_INCREMENT=8 DEFAULT CHARSET=utf8;
```


## version 0.2.6~

### 1. 檢舉功能新增資料庫欄位

#### 1.1 `forum_reply` 新增 被檢舉 欄位
```mysql
ALTER TABLE  `forum_reply` ADD  `reported` TINYINT NOT NULL COMMENT  '被檢舉' AFTER  `lastmod`
```
#### 1.2 新增 問題回報 資料表 `report_error`
```mysql
CREATE TABLE IF NOT EXISTS `report_error` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `admin_id` int(11) NOT NULL COMMENT '建立者',
  `url` varchar(255) NOT NULL,
  `type` varchar(255) NOT NULL,
  `content` text NOT NULL,
  `file_name` varchar(255) NOT NULL,
  `src_name` varchar(255) NOT NULL,
  `phone` int(11) NOT NULL,
  `school` varchar(255) NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  `processed` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```
#### 1.3 新增 討論區檢舉 資料表 `report_forum`
```mysql
CREATE TABLE IF NOT EXISTS `report_forum` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `type` enum('reply','question') NOT NULL DEFAULT 'reply',
  `admin_id` int(11) NOT NULL COMMENT '建立者',
  `course_id` int(11) NOT NULL,
  `forum_id` int(11) NOT NULL COMMENT '提問',
  `reply_id` int(11) NOT NULL COMMENT '留言',
  `content_admin_id` int(11) DEFAULT NULL COMMENT '被檢舉者',
  `content` text NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  `processed` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```

#### 1.4 新增 頁面檢舉 資料表 `report_page`
```mysql
CREATE TABLE IF NOT EXISTS `report_page` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `admin_id` int(11) NOT NULL,
  `reply_admin_id` int(11) NOT NULL COMMENT '被檢舉者',
  `url` varchar(255) NOT NULL,
  `type` varchar(255) NOT NULL,
  `content` text NOT NULL,
  `file_name` varchar(255) NOT NULL,
  `src_name` varchar(255) NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  `processed` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```


#### 1.5 設定檔 增加 Google recaptcha key 設定

https://developers.google.com/recaptcha/docs/start

Domains
```
localhost
lms-dev.learnmode.net
```

global.php
```
$config['g_recaptcha_sitekey'] = '6Le4HxcTAAAAAP4JS_LkRwXPGRUj3DneRj22-Ij_';
```

### 2. 在 user table 增加
```mysql
ALTER TABLE  `user` ADD  `identity` ENUM('student','teacher','other') COMMENT '身份'  AFTER  `description`;
ALTER TABLE  `user` ADD  `country` VARCHAR( 255 ) NOT NULL COMMENT '組織'  AFTER  `identity`;
ALTER TABLE  `user` ADD  `counties` VARCHAR( 255 ) NOT NULL COMMENT '組織'  AFTER  `country`;
ALTER TABLE  `user` ADD  `district` VARCHAR( 255 ) NOT NULL COMMENT '組織'  AFTER  `counties`;
ALTER TABLE  `user` ADD  `org_id` VARCHAR( 255 ) NOT NULL COMMENT '組織'  AFTER  `district`;
ALTER TABLE  `user` ADD  `start_year` VARCHAR( 255 ) NOT NULL COMMENT '開始時間'  AFTER  `org_id`;
ALTER TABLE  `user` ADD  `start_month` VARCHAR( 255 ) NOT NULL AFTER  `start_year`;
ALTER TABLE  `user` ADD  `student_id` VARCHAR( 255 ) NOT NULL COMMENT '學號'  AFTER  `start_month`;
ALTER TABLE  `user` ADD  `class` VARCHAR( 255 ) NOT NULL COMMENT '班級'  AFTER  `student_id`;
ALTER TABLE  `user` ADD  `class_no` VARCHAR( 255 ) NOT NULL COMMENT '座號'  AFTER  `class`;
ALTER TABLE  `user` ADD  `is_profile_complete` tinyint(4) DEFAULT 0 NOT NULL COMMENT '使用者資料是否完整'  AFTER  `class_no`;
ALTER TABLE  `user` ADD  `is_new_pwd` tinyint(4) DEFAULT 0 NOT NULL COMMENT '是否填入新密碼'  AFTER  `is_profile_complete`;
UPDATE `user` SET `is_new_pwd`= 1 WHERE `provider` != 'Social' and  `validate_status` = "1";
```

### 3. 修改 LMS server DB
```mysql
ALTER TABLE `book` CHANGE `state` `state` ENUM( 'queued', 'finished', 'failed', 'password' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL DEFAULT'queued'
```

### 4. 新增 廣告、好友連結和活動情報
```mysql
CREATE TABLE IF NOT EXISTS `advertisement` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL,
  `subject` varchar(255) NOT NULL,
  `orig_name` varchar(255) NOT NULL COMMENT '上傳檔案最初原始檔名',
  `file_name` varchar(255) NOT NULL COMMENT '檔案名稱，包含副檔名',
  `url` varchar(255) NOT NULL,
  `home_rank` int(11) NOT NULL DEFAULT '0',
  `publish` tinyint(1) NOT NULL,
  `lastmod` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `deleted` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;

CREATE TABLE IF NOT EXISTS `link` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL,
  `url` varchar(255) NOT NULL,
  `orig_name` varchar(255) NOT NULL COMMENT '上傳檔案最初原始檔名',
  `file_name` varchar(255) NOT NULL COMMENT '檔案名稱，包含副檔名',
  `home_rank` int(11) NOT NULL DEFAULT '0' COMMENT '首頁排序順序',
  `publish` tinyint(1) NOT NULL,
  `lastmod` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `deleted` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;

CREATE TABLE IF NOT EXISTS `activity` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL,
  `content` text NOT NULL,
  `tag` varchar(255) NOT NULL,
  `orig_name` varchar(255) NOT NULL COMMENT '上傳檔案最初原始檔名',
  `file_name` varchar(255) NOT NULL COMMENT '檔案名稱，包含副檔名',
  `home_rank` int(11) NOT NULL DEFAULT '0' COMMENT '首頁排序順序',
  `publish` tinyint(1) NOT NULL,
  `lastmod` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `deleted` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8;
```

### 5. school data 建立
#### 5.1 先CD到patch目錄位置
```linux
  cd /var/www/lms/patch
```
#### 5.2 檢查/var/www/lms/patch是否有data資料夾，沒有的話建立
```linux
  mkdir data
```
#### 5.3 將檔案上傳至server，並丟到/var/www/lms/patch/data資料夾，最後執行以下指令。
(檔案名稱必須與school_data.php裡面的filename一樣)
```linux
  php school_data.php
```

### 6. html meta keyword 變更
application/config/global.php
```php
  $config['html_keywords'] = "教育部推薦線上教育平台,快速備課系統,無紙化,柯P新政,信望愛文教基金會, Learnmode,學習吧,免費教學平台,教育网國小數學、國小自然、國中數學,國中補習,國中會考,高中數學,高中補習,高職、丙檢,K12,技職考試,指考,學測,統測,落點分析,轉學考,教甄,教檢,行動補習,線上補習,行動學習,數位學習,線上學習,翻轉學習,補救教學,偏鄉課輔,遠距,補習班,家教,先修,考古題,APP課程,教學影片,知識點,均一,飛番雲,酷課雲,1know,新北市E學園,learn, videos, lectures, practice, exercises, TED,skills,classroom,course";
```


## version 0.2.4~

### 1. 新增作業和作業繳交資料表欄位
```mysql
ALTER TABLE  `homework` ADD  `original_name` VARCHAR( 255 ) NOT NULL COMMENT '原始檔名'  AFTER  `file_size`;
ALTER TABLE  `homework_handin` ADD  `original_name` VARCHAR( 255 ) NOT NULL COMMENT '原始檔名'  AFTER  `file_size`;
```
### 2 執行patch 補default_cover 欄位空值問題
```shell
php /var/www/lms/patch/course_pic.php
```

### 3 增加網站關鍵字
config/global.php 編輯參數 
```php
如果在台灣或自己的localhost
<?php
$config['market'] = "Taiwan";
?>
如果在大陸
<?php
$config['market'] = "China";
?>
```

### 4. 修改參數設定
config/global.php 編輯參數 

$config['user_pic_limit']

$config['user_pic_allowed_types']
```php
<?php
$config['user_pic_limit'] = 15000000; //15mb
$config['user_pic_allowed_types'] = array('jpg', 'JPG', 'png', 'PNG', 'jpeg', 'JPEG');
?>
```

## version 0.2.2~0.2.3

### 1. 增加網站關鍵字
config/global.php 編輯參數 
```php
<?php
$config['html_keywords'] = "進修、考試、考古題、教育、翻轉、升學、高中生、高職生、學習、補習班";
?>
```

### 2. 課堂、書籍、影片、試卷資料庫增加推薦欄位
```mysql
ALTER TABLE  `book` ADD  `recommend` TINYINT NOT NULL COMMENT  'dopod推薦' AFTER  `browses`
ALTER TABLE  `course` ADD  `recommend` TINYINT NOT NULL COMMENT  'dopod推薦' AFTER  `browses`
ALTER TABLE  `video` ADD  `recommend` TINYINT NOT NULL COMMENT  'dopod推薦' AFTER  `browses`
ALTER TABLE  `test` ADD  `recommend` TINYINT NOT NULL COMMENT  'dopod推薦' AFTER  `browses`
```

### 3. 使用者資料庫增加Openid欄位
```mysql
ALTER TABLE user ADD guid VARCHAR(255) NOT NULL COMMENT "教育部個人代碼" AFTER google_uid;
```

### 4. 課堂資料庫增加主打課程欄位
```mysql
ALTER TABLE  `course` ADD  `major` TINYINT( 4 ) NOT NULL COMMENT  '主打課程' AFTER  `recommend`
```

### 5. 新增音檔
#### 5.1 新增音檔資料表 `audio`
```mysql
CREATE TABLE IF NOT EXISTS `audio` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hash` varchar(255) NOT NULL,
  `search_id` varchar(32) NOT NULL COMMENT '搜尋引擎server 資料 id',
  `course_id` int(11) NOT NULL COMMENT '所屬課程',
  `admin_id` int(11) NOT NULL COMMENT '建立者',
  `name` varchar(255) NOT NULL,
  `author` varchar(255) NOT NULL COMMENT '作者',
  `institution` varchar(255) NOT NULL COMMENT '機構',
  `publication_date` date NOT NULL COMMENT '發布日期',
  `public` tinyint(1) NOT NULL COMMENT '是否為開放教材',
  `publish` tinyint(4) NOT NULL,
  `publish_start` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' COMMENT '發布開始時間',
  `publish_end` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' COMMENT '發布結束時間',
  `description` text NOT NULL,
  `CC_type` enum('','by','by-nc','by-nc-sa','by-nd','by-nc-nd','by-sa') NOT NULL DEFAULT '',
  `tag` text NOT NULL,
  `file_name` varchar(255) NOT NULL COMMENT '目前檔名',
  `src_name` varchar(255) NOT NULL COMMENT '原始檔名',
  `file_size` int(11) NOT NULL COMMENT '檔案大小',
  `browses` int(11) NOT NULL COMMENT '瀏覽人數',
  `recommend` tinyint(4) NOT NULL COMMENT 'dopod推薦',
  `views` int(11) NOT NULL COMMENT '觀看人數',
  `downloads` int(11) NOT NULL COMMENT '下載人數',
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00' ON UPDATE CURRENT_TIMESTAMP,
  `deleted` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `course_id` (`course_id`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```
#### 5.2 `course_chapter` 資料表增加素材類型 `audio`
```mysql
ALTER TABLE `course_chapter` CHANGE `res_type` `res_type` ENUM( 'chapter', 'book', 'video', 'test', 'classroom', 'homework', 'audio' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOTNULL COMMENT '素材類型'
```

#### 5.3 修改global.php 增加音檔設定
```php
//audio
$config['audio_limit'] = 2000000000; //2gb
$config['audio_allowed_types'] = array('mp3', 'wav');
```

### 6. 課堂資料庫增加預設封面欄位
```mysql
ALTER TABLE  `course` ADD  `default_cover` VARCHAR( 255 )  AFTER  `file_cover_name`
```
### 7. 課堂章節資料表增加 res_no 欄位
#### 7.1 新增 course_chapter.res_no 欄位
```mysql
ALTER TABLE `course_chapter` ADD `res_no` INT( 11 ) NOT NULL COMMENT '同課堂中所有章節和素材順序' AFTER `no`
```
#### 7.2 執行新欄位內容建立 patch (course_chapter_no_fix.php)
```linux
php /var/www/lms/patch/course_chapter_no_fix.php
```
### 8. hotfix 更新daily report 資料表
#### 8.1 更新 daily_report.type 欄位 enum 類別
```mysql
ALTER TABLE  `daily_report` CHANGE  `type`  `type` ENUM(  'user_register',  'user_login_web',  'user_login_app',  'user_login_web_and_app',  'material_click', 'guest_material_click' ) CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL COMMENT '每日註冊開通人數, 每日Web登入人數, 每日App登入人數, 每日Web和App都登入人數, 每日素材點擊數, 單日不登入, 確使用素材人數'
```

### 9. 課程討論區資料庫增加的欄位
#### 9.1 增加課程討論區刪除時操作帳號的欄位
```mysql
ALTER TABLE  `forum` ADD  `deletedby` VARCHAR( 255 ) NOT NULL COMMENT  '刪除時操作帳號' AFTER  `lastmod`
```

#### 9.2 增加課程討論區回覆刪除時操作帳號的欄位
```mysql
ALTER TABLE  `forum_reply` ADD  `deletedby` VARCHAR( 255 ) NOT NULL COMMENT  '刪除時操作帳號' AFTER  `lastmod`
```

### 10. 試卷score欄位更新
#### 10.1 執行score內容更新 patch (test_score_count.php)
```linux
php /var/www/lms/patch/test_score_count.php
```

### 11. 進階搜尋科目增加"自然 "&"社會"
#### 11.1 更改config/global.php
```php
$config['adv_search_filter_category'] = array('國文','數學','英文','物理','化學','理化', '自然', '生物','地科', '社會','歷史','地理','公民');
```

## version 0.1.6~0.2.2

### **1. Google drive**
#### 1.1 新增資料表 `social_token`
```
CREATE TABLE IF NOT EXISTS `social_token` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_id` int(11) NOT NULL,
  `provider` varchar(100) NOT NULL,
  `type` enum('access_token','refresh_token','connected') NOT NULL,
  `uid` varchar(255) NOT NULL,
  `token` varchar(512) NOT NULL,
  `expire` int(11) NOT NULL,
  `lastmod` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `user_id` (`user_id`)
) ENGINE=MyISAM  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```

#### 1.2 修改global.php
```php
$config['google_server_api_key']  = '';
$config['google_browser_api_key'] = '';
$config['google_client_id']       = '';
$config['google_client_secret']   = '';
```

### **2. Test PDF 重新轉檔**
#### 2.1 執行 patch/patch_recreate_test_pdf_pages.php
```shell
php patch/patch_recreate_test_pdf_pages.php
```
### **3. 學習吧App**
#### 3.1 資料庫更新
```

ALTER TABLE user ADD browses INT NOT NULL COMMENT "瀏覽人數" AFTER description;
ALTER TABLE favorite CHANGE res_type res_type VARCHAR(255) NOT NULL COMMENT "類型";

```

#### 3.2 imagemagick轉圖
設定 `application/config/global.php` 的 `$config['identify_location']`
```php
$config['identify_location'] = '/usr/bin/identify';
```
執行 `patch/user_pic_fullsize.php`
```
php patch/user_pic_fullsize.php
```
### **4. APP櫥窗**
#### 4.1 新增資料表 `application`
```
CREATE TABLE IF NOT EXISTS `application` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `type` enum('manual','auto') NOT NULL DEFAULT 'manual',
  `hash` varchar(16) NOT NULL,
  `search_id` varchar(32) NOT NULL,
  `admin_id` int(11) NOT NULL,
  `publish` int(11) NOT NULL,
  `name` varchar(255) NOT NULL,
  `googleplay` varchar(255) NOT NULL,
  `itunes` varchar(255) NOT NULL,
  `wp` varchar(255) NOT NULL,
  `tag` text NOT NULL,
  `browses` int(11) NOT NULL,
  `downloads` int(11) NOT NULL,
  `publisher` varchar(255) NOT NULL,
  `description` text NOT NULL,
  `src_cover` varchar(255) NOT NULL,
  `src_img` varchar(255) NOT NULL,
  `icon` varchar(255) NOT NULL,
  `youtube1` varchar(255) NOT NULL,
  `youtube2` varchar(255) NOT NULL,
  `youtube3` varchar(255) NOT NULL,
  `enterdate` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `lastmod` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
  `deleted` tinyint(4) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8 AUTO_INCREMENT=0;
```
### **5. notification**
#### 5.1 資料表建立欄位`from_id`
```
php patch/notification.php
```
#### 5.2 crontab加入排程
```
0 3 * * * php bin/notification.php
```

### **6. 課程報表**
#### 6.1 重新計數資料表`course`老師與學生人數
```
php patch/count_course_user.php
```
### **7. 刪除lmadmin課程**
#### 7.1 刪除lmadmin的`course`與`course`下的教材 'video', 'book', 'test'
```
php patch/lmadmin_course_del.php
```
#### 7.2 search建立資料 將 `patch/search_add.php` 放在 `application/controllers`

執行連結 http://staging-lms.learnmode.net/search_add
執行連結 http://staging-lms.learnmode.net/search_add/patch

## version 0.1.4~0.1.6

### **1. 檢查資料表 book, test, classroom 添加 encoder_id, state 並修改設定global.php**
#### 1.1 檢查資料表book, test, classroom 是否有 `encoder_id` 與 `state`欄位

``` 
ALTER TABLE book
  ADD ( `encoder_id` int(11) NOT NULL COMMENT '轉檔ID',
        `state` enum('queued','finished','failed') NOT NULL DEFAULT 'queued' COMMENT '轉檔狀態');

ALTER TABLE test
  ADD ( `encoder_id` int(11) NOT NULL COMMENT '轉檔ID',
        `state` enum('queued','finished','failed') NOT NULL DEFAULT 'queued' COMMENT '轉檔狀態');

ALTER TABLE classroom
  ADD ( `encoder_id` int(11) NOT NULL COMMENT '轉檔ID',
        `state` enum('queued','finished','failed') NOT NULL DEFAULT 'queued' COMMENT '轉檔狀態');
```
#### 1.2 修改global.php

```php
//book
$config['book_allowed_types'] = array('pdf', 'docx', 'doc', 'pptx', 'ppt');
//test
$config['test_pdf_allowed_types'] = array('pdf', 'docx', 'doc', 'pptx', 'ppt');
//classroom
$config['classroom_allowed_types'] = array('pdf', 'docx', 'doc', 'pptx', 'ppt');

$config['video_encoder_server'] = 'http://staging.learnmode.net:8181/job'; //video 改 job
$config['video_job'] = 'video-encoder';
$config['pdf_job'] = 'office-to-pdf';
```

### **2. learning_log 轉 tincanapi**
#### 2.1 建立索引
```shell
mongo
use lms
db.learning_log.createIndex({id: NumberInt(1)}, {unique: true})
db.learning_log.createIndex({"actor.mbox": NumberInt(1), "verb.id": NumberInt(1), "object.definition.type": NumberInt(1), timestamp: NumberInt(-1)})
db.learning_log.createIndex({"verb.id": NumberInt(1), "object.definition.type": NumberInt(1)})
```
#### 2.2 修改global.php
```php
$config['mongo'] = 'localhost:27017';
```
#### 2.3 執行patch
將 `patch/tincanapi_patch.php` 放在 `application/controllers`
```shell
php index.php tincanapi_patch
```
### **3. config.js參數轉到global.php**
編輯 `applcation/controllers/config/global.php`

參數 $config['post_notification'] 改成 $config['notification_post']

添加2個參數
```php
$config['notification_enable'] = TRUE;
$config['notification_path'] = '/backend_api/notification/polling';
```

## version 0~0.1.4

### 1. 匯入lmadmin.user, course
匯入mongodb docilis.users與docilis.images

`patch/Migration_Lmadmin.php` 編輯參數 $lmadmin_root
```php
<?php
private $lmadmin_root = 'd:/xampp/htdocs/lmadmin_web'; // lmadmin_web路徑
?>
```
執行 `patch/Migration_Lmadmin.php`

### 2. 匯入lmadmin.book
`patch/Migration_Global.php` 編輯參數 $config['course_chapter']
```php
<?php
$config['course_chapter'] = 'LM 資料轉移';
?>
```
執行 `patch/Migration_PDF.php`

### 3. 匯入Course.video
執行 `patch/Migration_Video.php`

### 4. 補充user.uuid
執行 `patch/user_uuid.php`

### 5. 匯入practice
`patch/Migration_Practice.php` 編輯參數 $practiceRoot
```php
<?php
private $practiceRoot = "C:/website/practice";
?>
```
執行 `patch/Migration_Practice.php`

執行 `bin/test_rank.php`

### 6. user建立使用者課程數統計資料
執行 `patch/user_courses_add.php`

### 7. 匯入classroom
`patch/Migration_Classroom.php` 編輯參數 $dopodits_root
```php
<?php
private $dopodits_root = 'd:/xampp/htdocs/dopodits_web'; // dopodits_web路徑
?>
```
執行 `patch/Migration_Classroom.php`

### 8. 匯入learning log
執行 `patch/Migration_Learninglog.php`

### 9. tag建立知識點統計資料
執行 `patch/tag_add.php`


### 10. search建立資料
將 `patch/search_add.php` 放在 `application/controllers`

執行連結 http://staging-lms.learnmode.net/search_add
執行連結 http://staging-lms.learnmode.net/search_add/patch

用 CLI 跑請設定 config.php 的 base_url, 否則 image 的 URL 會變成 localhost
https://gitlab.learnmode.net/dopod-project/newlm_web/blob/develop/system/core/Config.php#L67

php index.php search_add
php index.php search_add/patch

#### 11. 增加進階搜尋參數設定
config/global.php 編輯參數 

$config['adv_search_filter_school']

$config['adv_search_filter_category']
```php
<?php
//advance search
$config['adv_search_filter_school'] = array('大學','五專','高職','高中','國中','國小');
$config['adv_search_filter_category'] = array('國文','數學','英文','物理','化學','理化','生物','地科','歷史','地理','公民');
?>
```