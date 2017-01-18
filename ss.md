<h2 id="version-0217">version 0.2.17</h2>



<h4 id="release-date-2016-12-30">release date: 2016-12-30</h4>



<div class="sequence-diagram"><svg height="140" version="1.1" width="168.60000038146973" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" style="overflow: hidden; position: relative; left: -0.5px; top: -0.166656px;"><desc>Created with Raphaël 2.1.2</desc><defs></defs><rect x="10" y="20" width="30.06666660308838" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="20" y="30" width="10.066666603088379" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="25.03333330154419" y="40" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">A</tspan></text><rect x="10" y="80" width="30.06666660308838" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="20" y="90" width="10.066666603088379" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="25.03333330154419" y="100" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">A</tspan></text><path style="" fill="none" stroke="#000000" d="M25.03333330154419,60L25.03333330154419,80" stroke-width="2"></path><rect x="60.06666660308838" y="20" width="29.233333587646484" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="70.2750015258789" y="30" width="9.233333587646484" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="74.68333339691162" y="40" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">B</tspan></text><rect x="60.06666660308838" y="80" width="29.233333587646484" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="70.2750015258789" y="90" width="9.233333587646484" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="74.68333339691162" y="100" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">B</tspan></text><path style="" fill="none" stroke="#000000" d="M74.68333339691162,60L74.68333339691162,80" stroke-width="2"></path><rect x="109.30000019073486" y="20" width="29.300000190734863" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="119.44999694824219" y="30" width="9.300000190734863" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="123.9500002861023" y="40" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">C</tspan></text><rect x="109.30000019073486" y="80" width="29.300000190734863" height="40" rx="0" ry="0" fill="none" stroke="#000000" style="" stroke-width="2"></rect><rect x="119.44999694824219" y="90" width="9.300000190734863" height="20" rx="0" ry="0" fill="#ffffff" stroke="none" style=""></rect><text style="text-anchor: middle; font-family: Andale Mono,monospace; font-size: 16px;" x="123.9500002861023" y="100" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000"><tspan dy="5">C</tspan></text><path style="" fill="none" stroke="#000000" d="M123.9500002861023,60L123.9500002861023,80" stroke-width="2"></path></svg></div>



<h3 id="1-classroomactivity-新增-bgimage-欄位">1. classroom_activity 新增 bg_image 欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`classroom_activity`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`bg_image`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'活動背景圖'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`src_cover`</span></span></code></pre>



<h3 id="2-course-新增-firstpublish-欄位">2. course 新增 first_publish 欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`first_publish`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-number">1</span> COMMENT  <span class="hljs-string">'第一次上架'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`copy_course_id`</span></span></code></pre>



<h2 id="version-0216">version 0.2.16</h2>



<h4 id="release-date-2016-12-02">release date: 2016-12-02</h4>



<h3 id="1-user-新增-orgname-欄位">1. user 新增 org_name 欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`org_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`org_id`</span>;</span></code></pre>



<h3 id="2-增加課堂活動圖片上傳格式">2. 增加課堂活動圖片上傳格式</h3>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'classroom_activity_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'jpg'</span>, <span class="hljs-string">'png'</span>, <span class="hljs-string">'JPG'</span>, <span class="hljs-string">'PNG'</span>);</code></pre>



<h2 id="version-0215">version 0.2.15</h2>



<h4 id="release-date-2016-10-28">release date: 2016-10-28</h4>



<h3 id="1-複製出configphp做為個別運行環境的設定文件">1. 複製出config.php做為個別運行環境的設定文件</h3>



<pre class="prettyprint"><code class=" hljs r">cp <span class="hljs-keyword">...</span>/config.sample.php <span class="hljs-keyword">...</span>/config.php</code></pre>



<h3 id="2-新增-coursecopyprogress-table">2. 新增 course_copy_progress table</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`course_copy_progress`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`course_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`user_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`state`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h2 id="version-0214">version 0.2.14</h2>



<h4 id="release-date-2016-10-07">release date: 2016-10-07</h4>



<h3 id="1-globalsamplephp-新增-首頁判斷變數">1. global.sample.php 新增 首頁判斷變數</h3>



<pre class="prettyprint"><code class=" hljs php"><span class="hljs-comment">//old, mess, makers</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'homepage'</span>] = <span class="hljs-string">"mess"</span>;</code></pre>



<h3 id="2-新增-accountgroup-table">2. 新增 account_group table</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`account_group`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`user_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`admin`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h3 id="3-新增-accountgroupuser-table">3. 新增 account_group_user table</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`account_group_user`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`group_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`teach_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`student_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h2 id="version-0213">version 0.2.13</h2>



<h4 id="release-date-2016-09-30">release date: 2016-09-30</h4>



<h3 id="1-增加daily-report的欄位內容">1. 增加daily report的欄位內容</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`daily_report`</span> CHANGE <span class="hljs-string">`type`</span> <span class="hljs-string">`type`</span> ENUM( <span class="hljs-string">'user_register'</span>, <span class="hljs-string">'user_register_append'</span>, <span class="hljs-string">'user_register_guest'</span>, <span class="hljs-string">'user_login_web'</span>, <span class="hljs-string">'user_login_app'</span>, <span class="hljs-string">'user_login_web_and_app'</span>, <span class="hljs-string">'material_click'</span>, <span class="hljs-string">'guest_material_click'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'單日註冊開通總人數, 單日附屬帳號數, 單日訪客數, 單日Web登入人數, 單日App登入人數, 單日Web和App都登入人數, 單日點擊素材人數, 單日不登入且點擊素材人數'</span></span></code></pre>



<h3 id="2-appendantmembershare-新增-isgroup-欄位">2. appendant_member_share 新增 is_group 欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`appendant_member_share`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`is_group`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`teach_id`</span>;</span></code></pre>



<h3 id="3-更新appversion">3. 更新app_version</h3>



<pre class="prettyprint"><code class="language-mysql hljs asciidoc">UPDATE <span class="hljs-smartquote">`app_version` SET `version`='</span>3.0.1',<span class="hljs-smartquote">`update_address`='</span>https://goo.gl/j00hsJ' WHERE <span class="hljs-smartquote">`name` = '</span>classroom'</code></pre>



<h2 id="version-0212">version 0.2.12</h2>



<h4 id="release-date-2016-09-02">release date: 2016-09-02</h4>



<h3 id="1-globalsamplephp-新增-副本系統email">1. global.sample.php 新增 副本系統email</h3>



<pre class="prettyprint"><code class=" hljs perl">//<span class="hljs-keyword">system</span> email
<span class="hljs-variable">$config</span>[<span class="hljs-string">'systemail_from'</span>] = <span class="hljs-string">"no-reply<span class="hljs-variable">@dopod</span>.com"</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'systemail_cc'</span>] = <span class="hljs-string">"service<span class="hljs-variable">@dopod</span>.com"</span>;</code></pre>



<h3 id="2-課程新增-是否開放複製欄位">2. 課程新增 是否開放複製欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`copy`</span> TINYINT( <span class="hljs-number">1</span> )  <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'是否開放複製'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`publish`</span></span></code></pre>



<h3 id="3-courseuser-新增-ta-teaching-assistant-角色">3. course_user 新增 ta (Teaching assistant) 角色</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course_user`</span> CHANGE  <span class="hljs-string">`role`</span>  <span class="hljs-string">`role`</span> ENUM(  <span class="hljs-string">'teacher'</span>,  <span class="hljs-string">'student'</span>,  <span class="hljs-string">'ta'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span></span></code></pre>



<h3 id="4-appversion">4. app_version</h3>



<h4 id="41-新增-updateaddress更新檔網址欄位">4.1 新增 update_address(更新檔網址)欄位</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`app_version`</span> <span class="hljs-keyword">ADD</span> <span class="hljs-string">`update_address`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>  COMMENT <span class="hljs-string">'更新檔網址'</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`version`</span>;</span></code></pre>



<h4 id="42-填入classroom-practice的更新檔網址">4.2 填入classroom, practice的更新檔網址</h4>



<pre class="prettyprint"><code class=" hljs http"><span class="hljs-attribute">classroom</span>: <span class="hljs-string">http://goo.gl/VmJkGh</span>
<span class="hljs-attribute">practice</span>: <span class="hljs-string"> http://goo.gl/1f2Ehv</span></code></pre>



<h4 id="43-新增account-manager版本資料">4.3 新增account manager版本資料</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">INSERT</span> <span class="hljs-keyword">INTO</span> <span class="hljs-string">`app_version`</span>(<span class="hljs-string">`name`</span>, <span class="hljs-string">`version`</span>, <span class="hljs-string">`update_address`</span>) <span class="hljs-keyword">VALUES</span> (<span class="hljs-string">'account_manager'</span>, <span class="hljs-string">'5.0.0'</span>, <span class="hljs-string">'http://goo.gl/idNXcZ'</span>);</span></code></pre>



<h3 id="5-hyperlink-新增-publish-欄位">5. hyperlink 新增 publish 欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`hyperlink`</span> <span class="hljs-keyword">ADD</span> <span class="hljs-string">`publish`</span> TINYINT( <span class="hljs-number">1</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'發佈,未發佈'</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`name`</span>;</span></code></pre>



<h3 id="6-補附屬帳號建立時間順序請cd至目錄位置cd-varwwwlmspatch">6. 補附屬帳號建立時間順序，請CD至目錄位置cd /var/www/lms/patch</h3>



<pre class="prettyprint"><code class="language-linux hljs avrasm">  php account_duration<span class="hljs-preprocessor">.php</span></code></pre>



<h3 id="7-重建questiontemplate的search資料">7. 重建question_template的search資料</h3>



<pre class="prettyprint"><code class=" hljs lasso">將 <span class="hljs-string">`patch/search_add.php`</span> 放在 <span class="hljs-string">`application/controllers`</span>
修改 <span class="hljs-keyword">private</span> <span class="hljs-variable">$search_type</span> <span class="hljs-subst">=</span> <span class="hljs-built_in">array</span>(<span class="hljs-string">'question_template'</span>);
修改 <span class="hljs-keyword">private</span> <span class="hljs-variable">$mysql_table</span> <span class="hljs-subst">=</span> <span class="hljs-built_in">array</span>(<span class="hljs-string">'question_template'</span>);

執行連結 http:<span class="hljs-comment">//staging-lms.learnmode.net/search_add</span>
執行連結 http:<span class="hljs-comment">//staging-lms.learnmode.net/search_add/patch</span></code></pre>



<h2 id="version-0211">version 0.2.11</h2>



<h3 id="1-增加-teacherreview-教師審核-資料表">1. 增加 teacher_review (教師審核) 資料表</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`teacher_review`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`user_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`contact_tel`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`service`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`certificate`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`content`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`inspector`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`state`</span> enum(<span class="hljs-string">'pending'</span>,<span class="hljs-string">'accepted'</span>,<span class="hljs-string">'rejected'</span>,<span class="hljs-string">'suspend'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> datetime <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h3 id="2-add-clientappid-and-clientappsecret-in-globalphp">2. add client_app_id and client_app_secret in global.php</h3>



<pre class="prettyprint"><code class="language-php hljs ">  <span class="hljs-variable">$config</span>[<span class="hljs-string">'client_app_id'</span>] = <span class="hljs-string">'superclient_app'</span>;
  <span class="hljs-variable">$config</span>[<span class="hljs-string">'client_app_secret'</span>] = <span class="hljs-string">'ad25df57e74bee7afd81994cc127f292338a6a54'</span>;</code></pre>



<h3 id="3-課程資料表-增加三個欄位">3. 課程資料表 增加三個欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`share`</span> TINYINT(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'共享'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`recommend`</span>
<span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`share_rank`</span> <span class="hljs-keyword">INT</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'首頁共享排序位置'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`home_rank`</span>
<span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`copy_course_id`</span> <span class="hljs-keyword">INT</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'複製的父課程ID'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`price`</span></span></code></pre>



<h3 id="4-新增附屬帳號表格">4. 新增附屬帳號表格</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql">  <span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`appendant_admin_user`</span> (
    <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
    <span class="hljs-string">`student_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
    <span class="hljs-string">`teach_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
    <span class="hljs-string">`admin`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
    <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
    <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
  ) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span>

  <span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`appendant_member_share`</span> (
    <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
    <span class="hljs-string">`share_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
    <span class="hljs-string">`teach_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
    <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
    <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
  ) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h3 id="5-修改user表格的permission欄位和新增studpwd欄位">5. 修改user表格的permission欄位和新增stud_pwd欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> CHANGE  <span class="hljs-string">`permission`</span>  <span class="hljs-string">`permission`</span> ENUM(  <span class="hljs-string">'admin'</span>, <span class="hljs-string">'teacher'</span>, <span class="hljs-string">'user'</span>, <span class="hljs-string">'student'</span>, <span class="hljs-string">'guest'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'"admin": 總管理員, "teacher": 教師, "student": 學生, "guest": 訪客'</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`stud_pwd`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'學生密碼'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`password`</span>;</span></code></pre>



<h3 id="6-增加-teacherreview-教師審核-資料表-欄位">6. 增加 teacher_review (教師審核) 資料表 欄位</h3>



<pre class="prettyprint"><code class=" hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`teacher_review`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`contact_phone`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'行動電話'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`user_id`</span></span></code></pre>



<h3 id="7-課程新增-課程代碼欄位">7. 課程新增 課程代碼欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`passcode`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">6</span>) COMMENT  <span class="hljs-string">'課程通行碼'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`hash`</span>;</span></code></pre>



<h3 id="8-add-importallowedtypes-in-globalphp">8. add import_allowed_types in global.php</h3>



<pre class="prettyprint"><code class="language-php hljs ">  <span class="hljs-comment">//virtual user import type</span>
  <span class="hljs-variable">$config</span>[<span class="hljs-string">'import_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'xlsx'</span>, <span class="hljs-string">'xls'</span>);</code></pre>



<h2 id="version-028增加兩個欄位">version 0.2.8~增加兩個欄位</h2>



<h3 id="1-超連結表格增加兩個欄位">1. 超連結表格增加兩個欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql">  <span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`hyperlink`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`admin_id`</span>;</span>
  <span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`hyperlink`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`description`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`name`</span>;</span></code></pre>



<h3 id="2-add-newbiecoursenumber-in-globalphp">2. add newbie_course_number in global.php</h3>



<pre class="prettyprint"><code class="language-php hljs ">  <span class="hljs-variable">$config</span>[<span class="hljs-string">'newbie_course_number'</span>] = <span class="hljs-string">'填入你的新手課程ID'</span>;</code></pre>



<h2 id="version-027">version 0.2.7~</h2>



<h3 id="1-課堂和影片資料表增加首頁顯示排序欄位">1. 課堂和影片資料表增加首頁顯示排序欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql">  <span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`home_rank`</span> <span class="hljs-keyword">INT</span>( <span class="hljs-number">11</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span>  <span class="hljs-string">'0'</span> COMMENT  <span class="hljs-string">'首頁顯示排序位置'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`major`</span>;</span>
  <span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`video`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`home_rank`</span> <span class="hljs-keyword">INT</span>( <span class="hljs-number">11</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span>  <span class="hljs-string">'0'</span> COMMENT  <span class="hljs-string">'首頁顯示排序位置'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`recommend`</span>;</span></code></pre>



<h3 id="2-add-knowledgeroot-and-knowledgeversionroot-settings-in-globalphp">2. add knowledge_root and Knowledge_version_root settings in global.php</h3>



<pre class="prettyprint"><code class="language-php hljs ">  <span class="hljs-variable">$config</span>[<span class="hljs-string">'knowledge_root'</span>] = <span class="hljs-number">2</span>;
  <span class="hljs-variable">$config</span>[<span class="hljs-string">'knowledge_version_root'</span>] = <span class="hljs-number">25</span>;</code></pre>



<h3 id="3-增加-coursechapter-素材屬性">3. 增加 course_chapter 素材屬性</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql">  <span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course_chapter`</span> CHANGE  <span class="hljs-string">`res_type`</span>  <span class="hljs-string">`res_type`</span> ENUM(  <span class="hljs-string">'chapter'</span>,  <span class="hljs-string">'book'</span>,  <span class="hljs-string">'video'</span>,  <span class="hljs-string">'test'</span>,  <span class="hljs-string">'classroom'</span>,  <span class="hljs-string">'homework'</span>,  <span class="hljs-string">'audio'</span>,  <span class="hljs-string">'hyperlink'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'素材類型'</span></span></code></pre>



<h3 id="4-增加-hyperlink-超連結-資料表">4. 增加 hyperlink (超連結) 資料表</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`hyperlink`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`course_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'所屬課程'</span>,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'建立者'</span>,
  <span class="hljs-string">`url`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`browses`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'瀏覽人數'</span>,
  <span class="hljs-string">`views`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'觀看人數'</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>),
  <span class="hljs-keyword">KEY</span> <span class="hljs-string">`course_id`</span> (<span class="hljs-string">`course_id`</span>)
) ENGINE=MyISAM AUTO_INCREMENT=<span class="hljs-number">8</span> <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h2 id="version-026">version 0.2.6~</h2>



<h3 id="1-檢舉功能新增資料庫欄位">1. 檢舉功能新增資料庫欄位</h3>



<h4 id="11-forumreply-新增-被檢舉-欄位">1.1 <code>forum_reply</code> 新增 被檢舉 欄位</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`forum_reply`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`reported`</span> TINYINT <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'被檢舉'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`lastmod`</span></span></code></pre>



<h4 id="12-新增-問題回報-資料表-reporterror">1.2 新增 問題回報 資料表 <code>report_error</code></h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`report_error`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'建立者'</span>,
  <span class="hljs-string">`url`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`type`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`content`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`src_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`phone`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`school`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`processed`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">1</span> ;</span></code></pre>



<h4 id="13-新增-討論區檢舉-資料表-reportforum">1.3 新增 討論區檢舉 資料表 <code>report_forum</code></h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`report_forum`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`type`</span> enum(<span class="hljs-string">'reply'</span>,<span class="hljs-string">'question'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'reply'</span>,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'建立者'</span>,
  <span class="hljs-string">`course_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`forum_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'提問'</span>,
  <span class="hljs-string">`reply_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'留言'</span>,
  <span class="hljs-string">`content_admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">DEFAULT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'被檢舉者'</span>,
  <span class="hljs-string">`content`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`processed`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">1</span> ;</span></code></pre>



<h4 id="14-新增-頁面檢舉-資料表-reportpage">1.4 新增 頁面檢舉 資料表 <code>report_page</code></h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`report_page`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`reply_admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'被檢舉者'</span>,
  <span class="hljs-string">`url`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`type`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`content`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`src_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`processed`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">1</span> ;</span></code></pre>



<h4 id="15-設定檔-增加-google-recaptcha-key-設定">1.5 設定檔 增加 Google recaptcha key 設定</h4>

<p><a href="https://developers.google.com/recaptcha/docs/start">https://developers.google.com/recaptcha/docs/start</a></p>

<p>Domains</p>



<pre class="prettyprint"><code class=" hljs avrasm">localhost
lms-dev<span class="hljs-preprocessor">.learnmode</span><span class="hljs-preprocessor">.net</span></code></pre>

<p>global.php</p>



<pre class="prettyprint"><code class=" hljs bash"><span class="hljs-variable">$config</span>[<span class="hljs-string">'g_recaptcha_sitekey'</span>] = <span class="hljs-string">'6Le4HxcTAAAAAP4JS_LkRwXPGRUj3DneRj22-Ij_'</span>;</code></pre>



<h3 id="2-在-user-table-增加">2. 在 user table 增加</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`identity`</span> ENUM(<span class="hljs-string">'student'</span>,<span class="hljs-string">'teacher'</span>,<span class="hljs-string">'other'</span>) COMMENT <span class="hljs-string">'身份'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`description`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`country`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'組織'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`identity`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`counties`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'組織'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`country`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`district`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'組織'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`counties`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`org_id`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'組織'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`district`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`start_year`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'開始時間'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`org_id`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`start_month`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`start_year`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`student_id`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'學號'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`start_month`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`class`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'班級'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`student_id`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`class_no`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'座號'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`class`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`is_profile_complete`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">DEFAULT</span> <span class="hljs-number">0</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'使用者資料是否完整'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`class_no`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`user`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`is_new_pwd`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">DEFAULT</span> <span class="hljs-number">0</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'是否填入新密碼'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`is_profile_complete`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">UPDATE</span> <span class="hljs-string">`user`</span> <span class="hljs-keyword">SET</span> <span class="hljs-string">`is_new_pwd`</span>= <span class="hljs-number">1</span> <span class="hljs-keyword">WHERE</span> <span class="hljs-string">`provider`</span> != <span class="hljs-string">'Social'</span> <span class="hljs-keyword">and</span>  <span class="hljs-string">`validate_status`</span> = <span class="hljs-string">"1"</span>;</span></code></pre>



<h3 id="3-修改-lms-server-db">3. 修改 LMS server DB</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`book`</span> CHANGE <span class="hljs-string">`state`</span> <span class="hljs-string">`state`</span> ENUM( <span class="hljs-string">'queued'</span>, <span class="hljs-string">'finished'</span>, <span class="hljs-string">'failed'</span>, <span class="hljs-string">'password'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span><span class="hljs-string">'queued'</span></span></code></pre>



<h3 id="4-新增-廣告好友連結和活動情報">4. 新增 廣告、好友連結和活動情報</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`advertisement`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`subject`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`orig_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'上傳檔案最初原始檔名'</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'檔案名稱，包含副檔名'</span>,
  <span class="hljs-string">`url`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`home_rank`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-string">`publish`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span>

<span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`link`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`url`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`orig_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'上傳檔案最初原始檔名'</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'檔案名稱，包含副檔名'</span>,
  <span class="hljs-string">`home_rank`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span> COMMENT <span class="hljs-string">'首頁排序順序'</span>,
  <span class="hljs-string">`publish`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span>

<span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`activity`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`content`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`tag`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`orig_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'上傳檔案最初原始檔名'</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'檔案名稱，包含副檔名'</span>,
  <span class="hljs-string">`home_rank`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span> COMMENT <span class="hljs-string">'首頁排序順序'</span>,
  <span class="hljs-string">`publish`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8;</span></code></pre>



<h3 id="5-school-data-建立">5. school data 建立</h3>



<h4 id="51-先cd到patch目錄位置">5.1 先CD到patch目錄位置</h4>



<pre class="prettyprint"><code class="language-linux hljs bash">  <span class="hljs-built_in">cd</span> /var/www/lms/patch</code></pre>



<h4 id="52-檢查varwwwlmspatch是否有data資料夾沒有的話建立">5.2 檢查/var/www/lms/patch是否有data資料夾，沒有的話建立</h4>



<pre class="prettyprint"><code class="language-linux hljs haskell">  mkdir <span class="hljs-typedef"><span class="hljs-keyword">data</span></span></code></pre>



<h4 id="53-將檔案上傳至server並丟到varwwwlmspatchdata資料夾最後執行以下指令">5.3 將檔案上傳至server，並丟到/var/www/lms/patch/data資料夾，最後執行以下指令。</h4>

<p>(檔案名稱必須與school_data.php裡面的filename一樣)</p>



<pre class="prettyprint"><code class="language-linux hljs avrasm">  php school_data<span class="hljs-preprocessor">.php</span></code></pre>



<h3 id="6-html-meta-keyword-變更">6. html meta keyword 變更</h3>

<p>application/config/global.php</p>



<pre class="prettyprint"><code class="language-php hljs ">  <span class="hljs-variable">$config</span>[<span class="hljs-string">'html_keywords'</span>] = <span class="hljs-string">"教育部推薦線上教育平台,快速備課系統,無紙化,柯P新政,信望愛文教基金會, Learnmode,學習吧,免費教學平台,教育网國小數學、國小自然、國中數學,國中補習,國中會考,高中數學,高中補習,高職、丙檢,K12,技職考試,指考,學測,統測,落點分析,轉學考,教甄,教檢,行動補習,線上補習,行動學習,數位學習,線上學習,翻轉學習,補救教學,偏鄉課輔,遠距,補習班,家教,先修,考古題,APP課程,教學影片,知識點,均一,飛番雲,酷課雲,1know,新北市E學園,learn, videos, lectures, practice, exercises, TED,skills,classroom,course"</span>;</code></pre>



<h2 id="version-024">version 0.2.4~</h2>



<h3 id="1-新增作業和作業繳交資料表欄位">1. 新增作業和作業繳交資料表欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`homework`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`original_name`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'原始檔名'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`file_size`</span>;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`homework_handin`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`original_name`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'原始檔名'</span>  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`file_size`</span>;</span></code></pre>



<h3 id="2-執行patch-補defaultcover-欄位空值問題">2 執行patch 補default_cover 欄位空值問題</h3>



<pre class="prettyprint"><code class="language-shell hljs cs">php /<span class="hljs-keyword">var</span>/www/lms/patch/course_pic.php</code></pre>



<h3 id="3-增加網站關鍵字">3 增加網站關鍵字</h3>

<p>config/global.php 編輯參數 </p>



<pre class="prettyprint"><code class="language-php hljs ">如果在台灣或自己的localhost
<span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'market'</span>] = <span class="hljs-string">"Taiwan"</span>;
<span class="hljs-preprocessor">?&gt;</span>
如果在大陸
<span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'market'</span>] = <span class="hljs-string">"China"</span>;
<span class="hljs-preprocessor">?&gt;</span></code></pre>



<h3 id="4-修改參數設定">4. 修改參數設定</h3>

<p>config/global.php 編輯參數 </p>

<p>$config[‘user_pic_limit’]</p>

<p>$config[‘user_pic_allowed_types’]</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'user_pic_limit'</span>] = <span class="hljs-number">15000000</span>; <span class="hljs-comment">//15mb</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'user_pic_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'jpg'</span>, <span class="hljs-string">'JPG'</span>, <span class="hljs-string">'png'</span>, <span class="hljs-string">'PNG'</span>, <span class="hljs-string">'jpeg'</span>, <span class="hljs-string">'JPEG'</span>);
<span class="hljs-preprocessor">?&gt;</span></code></pre>



<h2 id="version-022023">version 0.2.2~0.2.3</h2>



<h3 id="1-增加網站關鍵字">1. 增加網站關鍵字</h3>

<p>config/global.php 編輯參數 </p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'html_keywords'</span>] = <span class="hljs-string">"進修、考試、考古題、教育、翻轉、升學、高中生、高職生、學習、補習班"</span>;
<span class="hljs-preprocessor">?&gt;</span></code></pre>



<h3 id="2-課堂書籍影片試卷資料庫增加推薦欄位">2. 課堂、書籍、影片、試卷資料庫增加推薦欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`book`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`recommend`</span> TINYINT <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'dopod推薦'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`browses`</span>
<span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`recommend`</span> TINYINT <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'dopod推薦'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`browses`</span>
<span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`video`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`recommend`</span> TINYINT <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'dopod推薦'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`browses`</span>
<span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`test`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`recommend`</span> TINYINT <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'dopod推薦'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`browses`</span></span></code></pre>



<h3 id="3-使用者資料庫增加openid欄位">3. 使用者資料庫增加Openid欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">user</span> <span class="hljs-keyword">ADD</span> guid <span class="hljs-keyword">VARCHAR</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">"教育部個人代碼"</span> <span class="hljs-keyword">AFTER</span> google_uid;</span></code></pre>



<h3 id="4-課堂資料庫增加主打課程欄位">4. 課堂資料庫增加主打課程欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`major`</span> TINYINT( <span class="hljs-number">4</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'主打課程'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`recommend`</span></span></code></pre>



<h3 id="5-新增音檔">5. 新增音檔</h3>



<h4 id="51-新增音檔資料表-audio">5.1 新增音檔資料表 <code>audio</code></h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`audio`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`hash`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`search_id`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">32</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'搜尋引擎server 資料 id'</span>,
  <span class="hljs-string">`course_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'所屬課程'</span>,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'建立者'</span>,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`author`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'作者'</span>,
  <span class="hljs-string">`institution`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'機構'</span>,
  <span class="hljs-string">`publication_date`</span> <span class="hljs-keyword">date</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'發布日期'</span>,
  <span class="hljs-string">`public`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'是否為開放教材'</span>,
  <span class="hljs-string">`publish`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`publish_start`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> COMMENT <span class="hljs-string">'發布開始時間'</span>,
  <span class="hljs-string">`publish_end`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> COMMENT <span class="hljs-string">'發布結束時間'</span>,
  <span class="hljs-string">`description`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`CC_type`</span> enum(<span class="hljs-string">''</span>,<span class="hljs-string">'by'</span>,<span class="hljs-string">'by-nc'</span>,<span class="hljs-string">'by-nc-sa'</span>,<span class="hljs-string">'by-nd'</span>,<span class="hljs-string">'by-nc-nd'</span>,<span class="hljs-string">'by-sa'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">''</span>,
  <span class="hljs-string">`tag`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`file_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'目前檔名'</span>,
  <span class="hljs-string">`src_name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'原始檔名'</span>,
  <span class="hljs-string">`file_size`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'檔案大小'</span>,
  <span class="hljs-string">`browses`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'瀏覽人數'</span>,
  <span class="hljs-string">`recommend`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'dopod推薦'</span>,
  <span class="hljs-string">`views`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'觀看人數'</span>,
  <span class="hljs-string">`downloads`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'下載人數'</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">1</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0'</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>),
  <span class="hljs-keyword">KEY</span> <span class="hljs-string">`course_id`</span> (<span class="hljs-string">`course_id`</span>)
) ENGINE=MyISAM <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">1</span> ;</span></code></pre>



<h4 id="52-coursechapter-資料表增加素材類型-audio">5.2 <code>course_chapter</code> 資料表增加素材類型 <code>audio</code></h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`course_chapter`</span> CHANGE <span class="hljs-string">`res_type`</span> <span class="hljs-string">`res_type`</span> ENUM( <span class="hljs-string">'chapter'</span>, <span class="hljs-string">'book'</span>, <span class="hljs-string">'video'</span>, <span class="hljs-string">'test'</span>, <span class="hljs-string">'classroom'</span>, <span class="hljs-string">'homework'</span>, <span class="hljs-string">'audio'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci NOTNULL COMMENT <span class="hljs-string">'素材類型'</span></span></code></pre>



<h4 id="53-修改globalphp-增加音檔設定">5.3 修改global.php 增加音檔設定</h4>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-comment">//audio</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'audio_limit'</span>] = <span class="hljs-number">2000000000</span>; <span class="hljs-comment">//2gb</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'audio_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'mp3'</span>, <span class="hljs-string">'wav'</span>);</code></pre>



<h3 id="6-課堂資料庫增加預設封面欄位">6. 課堂資料庫增加預設封面欄位</h3>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`course`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`default_cover`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> )  <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`file_cover_name`</span></span></code></pre>



<h3 id="7-課堂章節資料表增加-resno-欄位">7. 課堂章節資料表增加 res_no 欄位</h3>



<h4 id="71-新增-coursechapterresno-欄位">7.1 新增 course_chapter.res_no 欄位</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-string">`course_chapter`</span> <span class="hljs-keyword">ADD</span> <span class="hljs-string">`res_no`</span> <span class="hljs-keyword">INT</span>( <span class="hljs-number">11</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'同課堂中所有章節和素材順序'</span> <span class="hljs-keyword">AFTER</span> <span class="hljs-string">`no`</span></span></code></pre>



<h4 id="72-執行新欄位內容建立-patch-coursechapternofixphp">7.2 執行新欄位內容建立 patch (course_chapter_no_fix.php)</h4>



<pre class="prettyprint"><code class="language-linux hljs cs">php /<span class="hljs-keyword">var</span>/www/lms/patch/course_chapter_no_fix.php</code></pre>



<h3 id="8-hotfix-更新daily-report-資料表">8. hotfix 更新daily report 資料表</h3>



<h4 id="81-更新-dailyreporttype-欄位-enum-類別">8.1 更新 daily_report.type 欄位 enum 類別</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`daily_report`</span> CHANGE  <span class="hljs-string">`type`</span>  <span class="hljs-string">`type`</span> ENUM(  <span class="hljs-string">'user_register'</span>,  <span class="hljs-string">'user_login_web'</span>,  <span class="hljs-string">'user_login_app'</span>,  <span class="hljs-string">'user_login_web_and_app'</span>,  <span class="hljs-string">'material_click'</span>, <span class="hljs-string">'guest_material_click'</span> ) <span class="hljs-keyword">CHARACTER</span> <span class="hljs-keyword">SET</span> utf8 <span class="hljs-keyword">COLLATE</span> utf8_general_ci <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'每日註冊開通人數, 每日Web登入人數, 每日App登入人數, 每日Web和App都登入人數, 每日素材點擊數, 單日不登入, 確使用素材人數'</span></span></code></pre>



<h3 id="9-課程討論區資料庫增加的欄位">9. 課程討論區資料庫增加的欄位</h3>



<h4 id="91-增加課程討論區刪除時操作帳號的欄位">9.1 增加課程討論區刪除時操作帳號的欄位</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`forum`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`deletedby`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'刪除時操作帳號'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`lastmod`</span></span></code></pre>



<h4 id="92-增加課程討論區回覆刪除時操作帳號的欄位">9.2 增加課程討論區回覆刪除時操作帳號的欄位</h4>



<pre class="prettyprint"><code class="language-mysql hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span>  <span class="hljs-string">`forum_reply`</span> <span class="hljs-keyword">ADD</span>  <span class="hljs-string">`deletedby`</span> <span class="hljs-keyword">VARCHAR</span>( <span class="hljs-number">255</span> ) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT  <span class="hljs-string">'刪除時操作帳號'</span> <span class="hljs-keyword">AFTER</span>  <span class="hljs-string">`lastmod`</span></span></code></pre>



<h3 id="10-試卷score欄位更新">10. 試卷score欄位更新</h3>



<h4 id="101-執行score內容更新-patch-testscorecountphp">10.1 執行score內容更新 patch (test_score_count.php)</h4>



<pre class="prettyprint"><code class="language-linux hljs cs">php /<span class="hljs-keyword">var</span>/www/lms/patch/test_score_count.php</code></pre>



<h3 id="11-進階搜尋科目增加自然-社會">11. 進階搜尋科目增加”自然 “&amp;”社會”</h3>



<h4 id="111-更改configglobalphp">11.1 更改config/global.php</h4>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'adv_search_filter_category'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'國文'</span>,<span class="hljs-string">'數學'</span>,<span class="hljs-string">'英文'</span>,<span class="hljs-string">'物理'</span>,<span class="hljs-string">'化學'</span>,<span class="hljs-string">'理化'</span>, <span class="hljs-string">'自然'</span>, <span class="hljs-string">'生物'</span>,<span class="hljs-string">'地科'</span>, <span class="hljs-string">'社會'</span>,<span class="hljs-string">'歷史'</span>,<span class="hljs-string">'地理'</span>,<span class="hljs-string">'公民'</span>);</code></pre>



<h2 id="version-016022">version 0.1.6~0.2.2</h2>



<h3 id="1-google-drive"><strong>1. Google drive</strong></h3>



<h4 id="11-新增資料表-socialtoken">1.1 新增資料表 <code>social_token</code></h4>



<pre class="prettyprint"><code class=" hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`social_token`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`user_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`provider`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">100</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`type`</span> enum(<span class="hljs-string">'access_token'</span>,<span class="hljs-string">'refresh_token'</span>,<span class="hljs-string">'connected'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`uid`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`token`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">512</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`expire`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span> <span class="hljs-keyword">ON</span> <span class="hljs-keyword">UPDATE</span> <span class="hljs-keyword">CURRENT_TIMESTAMP</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>),
  <span class="hljs-keyword">KEY</span> <span class="hljs-string">`user_id`</span> (<span class="hljs-string">`user_id`</span>)
) ENGINE=MyISAM  <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">1</span> ;</span></code></pre>



<h4 id="12-修改globalphp">1.2 修改global.php</h4>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'google_server_api_key'</span>]  = <span class="hljs-string">''</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'google_browser_api_key'</span>] = <span class="hljs-string">''</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'google_client_id'</span>]       = <span class="hljs-string">''</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'google_client_secret'</span>]   = <span class="hljs-string">''</span>;</code></pre>



<h3 id="2-test-pdf-重新轉檔"><strong>2. Test PDF 重新轉檔</strong></h3>



<h4 id="21-執行-patchpatchrecreatetestpdfpagesphp">2.1 執行 patch/patch_recreate_test_pdf_pages.php</h4>



<pre class="prettyprint"><code class="language-shell hljs glsl">php <span class="hljs-keyword">patch</span>/patch_recreate_test_pdf_pages.php</code></pre>



<h3 id="3-學習吧app"><strong>3. 學習吧App</strong></h3>



<h4 id="31-資料庫更新">3.1 資料庫更新</h4>



<pre class="prettyprint"><code class=" hljs sql">
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">user</span> <span class="hljs-keyword">ADD</span> browses <span class="hljs-keyword">INT</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">"瀏覽人數"</span> <span class="hljs-keyword">AFTER</span> description;</span>
<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> favorite CHANGE res_type res_type <span class="hljs-keyword">VARCHAR</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">"類型"</span>;</span>
</code></pre>



<h4 id="32-imagemagick轉圖">3.2 imagemagick轉圖</h4>

<p>設定 <code>application/config/global.php</code> 的 <code>$config['identify_location']</code></p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'identify_location'</span>] = <span class="hljs-string">'/usr/bin/identify'</span>;</code></pre>

<p>執行 <code>patch/user_pic_fullsize.php</code></p>



<pre class="prettyprint"><code class=" hljs glsl">php <span class="hljs-keyword">patch</span>/user_pic_fullsize.php</code></pre>



<h3 id="4-app櫥窗"><strong>4. APP櫥窗</strong></h3>



<h4 id="41-新增資料表-application">4.1 新增資料表 <code>application</code></h4>



<pre class="prettyprint"><code class=" hljs sql"><span class="hljs-operator"><span class="hljs-keyword">CREATE</span> <span class="hljs-keyword">TABLE</span> <span class="hljs-keyword">IF</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">EXISTS</span> <span class="hljs-string">`application`</span> (
  <span class="hljs-string">`id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> AUTO_INCREMENT,
  <span class="hljs-string">`type`</span> enum(<span class="hljs-string">'manual'</span>,<span class="hljs-string">'auto'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'manual'</span>,
  <span class="hljs-string">`hash`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">16</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`search_id`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">32</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`admin_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`publish`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`name`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`googleplay`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`itunes`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`wp`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`tag`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`browses`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`downloads`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`publisher`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`description`</span> text <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`src_cover`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`src_img`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`icon`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`youtube1`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`youtube2`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`youtube3`</span> <span class="hljs-keyword">varchar</span>(<span class="hljs-number">255</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-string">`enterdate`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`lastmod`</span> <span class="hljs-keyword">timestamp</span> <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'0000-00-00 00:00:00'</span>,
  <span class="hljs-string">`deleted`</span> tinyint(<span class="hljs-number">4</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span>,
  <span class="hljs-keyword">PRIMARY</span> <span class="hljs-keyword">KEY</span> (<span class="hljs-string">`id`</span>)
) ENGINE=MyISAM <span class="hljs-keyword">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="hljs-number">0</span>;</span></code></pre>



<h3 id="5-notification"><strong>5. notification</strong></h3>



<h4 id="51-資料表建立欄位fromid">5.1 資料表建立欄位<code>from_id</code></h4>



<pre class="prettyprint"><code class=" hljs glsl">php <span class="hljs-keyword">patch</span>/notification.php</code></pre>



<h4 id="52-crontab加入排程">5.2 crontab加入排程</h4>



<pre class="prettyprint"><code class=" hljs markdown">0 3 <span class="hljs-bullet">* *</span> * php bin/notification.php</code></pre>



<h3 id="6-課程報表"><strong>6. 課程報表</strong></h3>



<h4 id="61-重新計數資料表course老師與學生人數">6.1 重新計數資料表<code>course</code>老師與學生人數</h4>



<pre class="prettyprint"><code class=" hljs glsl">php <span class="hljs-keyword">patch</span>/count_course_user.php</code></pre>



<h3 id="7-刪除lmadmin課程"><strong>7. 刪除lmadmin課程</strong></h3>



<h4 id="71-刪除lmadmin的course與course下的教材-video-book-test">7.1 刪除lmadmin的<code>course</code>與<code>course</code>下的教材 ‘video’, ‘book’, ‘test’</h4>



<pre class="prettyprint"><code class=" hljs glsl">php <span class="hljs-keyword">patch</span>/lmadmin_course_del.php</code></pre>



<h4 id="72-search建立資料-將-patchsearchaddphp-放在-applicationcontrollers">7.2 search建立資料 將 <code>patch/search_add.php</code> 放在 <code>application/controllers</code></h4>

<p>執行連結 <a href="http://staging-lms.learnmode.net/search_add">http://staging-lms.learnmode.net/search_add</a> <br>
執行連結 <a href="http://staging-lms.learnmode.net/search_add/patch">http://staging-lms.learnmode.net/search_add/patch</a></p>



<h2 id="version-014016">version 0.1.4~0.1.6</h2>



<h3 id="1-檢查資料表-book-test-classroom-添加-encoderid-state-並修改設定globalphp"><strong>1. 檢查資料表 book, test, classroom 添加 encoder_id, state 並修改設定global.php</strong></h3>



<h4 id="11-檢查資料表book-test-classroom-是否有-encoderid-與-state欄位">1.1 檢查資料表book, test, classroom 是否有 <code>encoder_id</code> 與 <code>state</code>欄位</h4>



<pre class="prettyprint"><code class=" hljs sql"><span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> book
  <span class="hljs-keyword">ADD</span> ( <span class="hljs-string">`encoder_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'轉檔ID'</span>,
        <span class="hljs-string">`state`</span> enum(<span class="hljs-string">'queued'</span>,<span class="hljs-string">'finished'</span>,<span class="hljs-string">'failed'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'queued'</span> COMMENT <span class="hljs-string">'轉檔狀態'</span>);</span>

<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> test
  <span class="hljs-keyword">ADD</span> ( <span class="hljs-string">`encoder_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'轉檔ID'</span>,
        <span class="hljs-string">`state`</span> enum(<span class="hljs-string">'queued'</span>,<span class="hljs-string">'finished'</span>,<span class="hljs-string">'failed'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'queued'</span> COMMENT <span class="hljs-string">'轉檔狀態'</span>);</span>

<span class="hljs-operator"><span class="hljs-keyword">ALTER</span> <span class="hljs-keyword">TABLE</span> classroom
  <span class="hljs-keyword">ADD</span> ( <span class="hljs-string">`encoder_id`</span> <span class="hljs-keyword">int</span>(<span class="hljs-number">11</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> COMMENT <span class="hljs-string">'轉檔ID'</span>,
        <span class="hljs-string">`state`</span> enum(<span class="hljs-string">'queued'</span>,<span class="hljs-string">'finished'</span>,<span class="hljs-string">'failed'</span>) <span class="hljs-keyword">NOT</span> <span class="hljs-keyword">NULL</span> <span class="hljs-keyword">DEFAULT</span> <span class="hljs-string">'queued'</span> COMMENT <span class="hljs-string">'轉檔狀態'</span>);</span></code></pre>



<h4 id="12-修改globalphp-1">1.2 修改global.php</h4>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-comment">//book</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'book_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'pdf'</span>, <span class="hljs-string">'docx'</span>, <span class="hljs-string">'doc'</span>, <span class="hljs-string">'pptx'</span>, <span class="hljs-string">'ppt'</span>);
<span class="hljs-comment">//test</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'test_pdf_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'pdf'</span>, <span class="hljs-string">'docx'</span>, <span class="hljs-string">'doc'</span>, <span class="hljs-string">'pptx'</span>, <span class="hljs-string">'ppt'</span>);
<span class="hljs-comment">//classroom</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'classroom_allowed_types'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'pdf'</span>, <span class="hljs-string">'docx'</span>, <span class="hljs-string">'doc'</span>, <span class="hljs-string">'pptx'</span>, <span class="hljs-string">'ppt'</span>);

<span class="hljs-variable">$config</span>[<span class="hljs-string">'video_encoder_server'</span>] = <span class="hljs-string">'http://staging.learnmode.net:8181/job'</span>; <span class="hljs-comment">//video 改 job</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'video_job'</span>] = <span class="hljs-string">'video-encoder'</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'pdf_job'</span>] = <span class="hljs-string">'office-to-pdf'</span>;</code></pre>



<h3 id="2-learninglog-轉-tincanapi"><strong>2. learning_log 轉 tincanapi</strong></h3>



<h4 id="21-建立索引">2.1 建立索引</h4>



<pre class="prettyprint"><code class="language-shell hljs avrasm">mongo
use lms
db<span class="hljs-preprocessor">.learning</span>_log<span class="hljs-preprocessor">.createIndex</span>({id: NumberInt(<span class="hljs-number">1</span>)}, {unique: true})
db<span class="hljs-preprocessor">.learning</span>_log<span class="hljs-preprocessor">.createIndex</span>({<span class="hljs-string">"actor.mbox"</span>: NumberInt(<span class="hljs-number">1</span>), <span class="hljs-string">"verb.id"</span>: NumberInt(<span class="hljs-number">1</span>), <span class="hljs-string">"object.definition.type"</span>: NumberInt(<span class="hljs-number">1</span>), timestamp: NumberInt(-<span class="hljs-number">1</span>)})
db<span class="hljs-preprocessor">.learning</span>_log<span class="hljs-preprocessor">.createIndex</span>({<span class="hljs-string">"verb.id"</span>: NumberInt(<span class="hljs-number">1</span>), <span class="hljs-string">"object.definition.type"</span>: NumberInt(<span class="hljs-number">1</span>)})</code></pre>



<h4 id="22-修改globalphp">2.2 修改global.php</h4>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'mongo'</span>] = <span class="hljs-string">'localhost:27017'</span>;</code></pre>



<h4 id="23-執行patch">2.3 執行patch</h4>

<p>將 <code>patch/tincanapi_patch.php</code> 放在 <code>application/controllers</code></p>



<pre class="prettyprint"><code class="language-shell hljs axapta">php <span class="hljs-keyword">index</span>.php tincanapi_patch</code></pre>



<h3 id="3-configjs參數轉到globalphp"><strong>3. config.js參數轉到global.php</strong></h3>

<p>編輯 <code>applcation/controllers/config/global.php</code></p>

<p>參數 <script type="math/tex" id="MathJax-Element-1">config['post_notification'] 改成 </script>config[‘notification_post’]</p>

<p>添加2個參數</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-variable">$config</span>[<span class="hljs-string">'notification_enable'</span>] = <span class="hljs-keyword">TRUE</span>;
<span class="hljs-variable">$config</span>[<span class="hljs-string">'notification_path'</span>] = <span class="hljs-string">'/backend_api/notification/polling'</span>;</code></pre>



<h2 id="version-0014">version 0~0.1.4</h2>



<h3 id="1-匯入lmadminuser-course">1. 匯入lmadmin.user, course</h3>

<p>匯入mongodb docilis.users與docilis.images</p>

<p><code>patch/Migration_Lmadmin.php</code> 編輯參數 $lmadmin_root</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-keyword">private</span> <span class="hljs-variable">$lmadmin_root</span> = <span class="hljs-string">'d:/xampp/htdocs/lmadmin_web'</span>; <span class="hljs-comment">// lmadmin_web路徑</span>
<span class="hljs-preprocessor">?&gt;</span></code></pre>

<p>執行 <code>patch/Migration_Lmadmin.php</code></p>



<h3 id="2-匯入lmadminbook">2. 匯入lmadmin.book</h3>

<p><code>patch/Migration_Global.php</code> 編輯參數 $config[‘course_chapter’]</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'course_chapter'</span>] = <span class="hljs-string">'LM 資料轉移'</span>;
<span class="hljs-preprocessor">?&gt;</span></code></pre>

<p>執行 <code>patch/Migration_PDF.php</code></p>



<h3 id="3-匯入coursevideo">3. 匯入Course.video</h3>

<p>執行 <code>patch/Migration_Video.php</code></p>



<h3 id="4-補充useruuid">4. 補充user.uuid</h3>

<p>執行 <code>patch/user_uuid.php</code></p>



<h3 id="5-匯入practice">5. 匯入practice</h3>

<p><code>patch/Migration_Practice.php</code> 編輯參數 $practiceRoot</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-keyword">private</span> <span class="hljs-variable">$practiceRoot</span> = <span class="hljs-string">"C:/website/practice"</span>;
<span class="hljs-preprocessor">?&gt;</span></code></pre>

<p>執行 <code>patch/Migration_Practice.php</code></p>

<p>執行 <code>bin/test_rank.php</code></p>



<h3 id="6-user建立使用者課程數統計資料">6. user建立使用者課程數統計資料</h3>

<p>執行 <code>patch/user_courses_add.php</code></p>



<h3 id="7-匯入classroom">7. 匯入classroom</h3>

<p><code>patch/Migration_Classroom.php</code> 編輯參數 $dopodits_root</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-keyword">private</span> <span class="hljs-variable">$dopodits_root</span> = <span class="hljs-string">'d:/xampp/htdocs/dopodits_web'</span>; <span class="hljs-comment">// dopodits_web路徑</span>
<span class="hljs-preprocessor">?&gt;</span></code></pre>

<p>執行 <code>patch/Migration_Classroom.php</code></p>



<h3 id="8-匯入learning-log">8. 匯入learning log</h3>

<p>執行 <code>patch/Migration_Learninglog.php</code></p>



<h3 id="9-tag建立知識點統計資料">9. tag建立知識點統計資料</h3>

<p>執行 <code>patch/tag_add.php</code></p>



<h3 id="10-search建立資料">10. search建立資料</h3>

<p>將 <code>patch/search_add.php</code> 放在 <code>application/controllers</code></p>

<p>執行連結 <a href="http://staging-lms.learnmode.net/search_add">http://staging-lms.learnmode.net/search_add</a> <br>
執行連結 <a href="http://staging-lms.learnmode.net/search_add/patch">http://staging-lms.learnmode.net/search_add/patch</a></p>

<p>用 CLI 跑請設定 config.php 的 base_url, 否則 image 的 URL 會變成 localhost <br>
<a href="https://gitlab.learnmode.net/dopod-project/newlm_web/blob/develop/system/core/Config.php#L67">https://gitlab.learnmode.net/dopod-project/newlm_web/blob/develop/system/core/Config.php#L67</a></p>

<p>php index.php search_add <br>
php index.php search_add/patch</p>



<h4 id="11-增加進階搜尋參數設定">11. 增加進階搜尋參數設定</h4>

<p>config/global.php 編輯參數 </p>

<p>$config[‘adv_search_filter_school’]</p>

<p>$config[‘adv_search_filter_category’]</p>



<pre class="prettyprint"><code class="language-php hljs "><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-comment">//advance search</span>
<span class="hljs-variable">$config</span>[<span class="hljs-string">'adv_search_filter_school'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'大學'</span>,<span class="hljs-string">'五專'</span>,<span class="hljs-string">'高職'</span>,<span class="hljs-string">'高中'</span>,<span class="hljs-string">'國中'</span>,<span class="hljs-string">'國小'</span>);
<span class="hljs-variable">$config</span>[<span class="hljs-string">'adv_search_filter_category'</span>] = <span class="hljs-keyword">array</span>(<span class="hljs-string">'國文'</span>,<span class="hljs-string">'數學'</span>,<span class="hljs-string">'英文'</span>,<span class="hljs-string">'物理'</span>,<span class="hljs-string">'化學'</span>,<span class="hljs-string">'理化'</span>,<span class="hljs-string">'生物'</span>,<span class="hljs-string">'地科'</span>,<span class="hljs-string">'歷史'</span>,<span class="hljs-string">'地理'</span>,<span class="hljs-string">'公民'</span>);
<span class="hljs-preprocessor">?&gt;</span></code></pre>