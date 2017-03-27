長庚大學 大數據分析方法 作業三
================

網站資料爬取
------------

``` r
library(rvest)
```

    ## Warning: package 'rvest' was built under R version 3.3.3

    ## Loading required package: xml2

    ## Warning: package 'xml2' was built under R version 3.3.3

``` r
PttMovie1<-"https://www.ptt.cc/bbs/movie/index5248.html"
PttMovie2<-"https://www.ptt.cc/bbs/movie/index5247.html"
PttMovie3<-"https://www.ptt.cc/bbs/movie/index5246.html"
PttMovie4<-"https://www.ptt.cc/bbs/movie/index5245.html"
PttMovie5<-"https://www.ptt.cc/bbs/movie/index5244.html"
a<-c(PttMovie1,PttMovie2,PttMovie3,PttMovie4,PttMovie5)

dataframeAll<-NULL  ##避免之前跑過的未清空
for(n in a){
    
        Title<-read_html(n) %>%html_nodes(".title") %>% html_text()
        PushNum<-read_html(n) %>% html_nodes(".nrec") %>% html_text()
        Author<-read_html(n) %>%html_nodes(".author") %>% html_text()
        dataframe<- data.frame(Title=Title,PushNum=PushNum,Author=Author) 
        
    dataframeAll<-rbind(dataframeAll,dataframe)
    } 
```

爬蟲結果呈現
------------

``` r
knitr::kable(dataframeAll)
```

| Title                                               | PushNum | Author       |
|:----------------------------------------------------|:--------|:-------------|
| \[新聞\] 《長城》太驚人　景甜二度登基爛片女帝       | 24      | vm04vm04     |
| \[討論\] 最愛安海瑟威演的哪部片                     | 78      | litann4      |
| Re: \[討論\] Emma Watson是不是只能演小女生？        | 9       | denverkober  |
| \[贈票\]【攻殼機動隊】IMAX 3D 14分鐘特別片段        | 爆      | ChloeD       |
| \[討論\] 金剛:骷髏島，女主角的相機                  | 7       | kiwistar     |
| \[問片\] 很久很久的電影不知道片名                   | 6       | fish60233    |
| \[新聞\] 曾經轟動全台！「魔鬼終結者2」3D版今秋      | 29      | fff15973     |
| \[好雷\] 絕鯊島The Shallows                         | 15      | ueiwei       |
| \[贈票\] 橫掃義大利金獎大導《媽媽教我愛的一切》     | 72      | indiasosp    |
| \[討論\] 祝多藍生日快樂，這個多藍好日系             | 4       | r123tw       |
| \[新聞\] 景甜俏麗套GUCCI　黏邪神洩綜藝魂            | 27      | shinbird     |
| \[好雷\] 美女與野獸<sub>我看的是童年不是童話</sub>  | 31      | tsukachan    |
| \[普雷\]《乘風破浪》- 韓寒呼叫1998                  | 1       | jk10134      |
| \[微好雷\] 當他們認真編織時                         | 3       | u850234      |
| \[好雷\] 奔奔奔 Burn Burn Burn，唐頓二姐壓馬路      | 2       | mysmalllamb  |
| Re: \[LIVE\] 刺激1995 AXN 21:00                     | 3       | Sturmvogel   |
| \[問片\] 找一部夫妻被綁，妻子卻與綁匪%%%            | 17      | ejijo761115  |
| \[好雷\] 真人版《美女與野獸》最喜歡的改編？         | 15      | freiheitkino |
| \[情報\] 韓國電影《叛獄無間》4/7在台上映            | 4       | LeedTV       |
| \[普雷\] 美女與野獸小吐槽                           | 38      | sarasay      |
| \[好雷\] 美女與野獸隨筆心得                         | 3       | MYLIUUU      |
| \[普偏好雷\]美女與野獸 比預期普通一些               | 20      | s2657507     |
| Re: \[超爛雷\] 自殺小隊，連BvS都可以屌打這部爛片    | 9       | KingKingCold |
| \[好雷\] 美女與野獸--野獸長大了                     | 12      | COCOCCC      |
| Re: \[請益\] 明天，我要和昨天的妳約會 時間線        | 7       | nasuchan     |
| \[贈票\] 3/29金馬奇幻影展特映會                     | 1       | mid729       |
| Fw: \[閒聊\] 誤闖進 Cyberpunk潮流的香港九龍城寨     | 4       | patdolye     |
| \[新聞\] 艾莉西亞薇坎德將演出摩天樓導演新片         | 6       | sampsonlu919 |
| Re: \[失望雷\] 羅根 確認福斯真的沒心經營X戰警系列   | 20      | tomgod17     |
| \[普好雷\] 完全沒看過X戰警下的羅根觀感              | 16      | NCKUFatPork  |
| \[片單\] 青貧世代議題電影推薦                       | 16      | ragnarokfans |
| \[好雷\] 《三笑》(1964)（主談秋香）                 | 8       | metz1552     |
| \[好雷\] 美女與野獸，重新認識貝兒                   | 2       | Edouard      |
| \[新聞\] 裸照門爆75人名單 泰勒絲布麗拉森驚駭        | 10      | zkow         |
| \[新聞\] 史嘉蕾拍片集郵亞洲城市 憶《露西》讚台北    | 16      | zkow         |
| \[新聞\] 美女與野獸 首週末全球票房3.5億美元         | 79      | lovemelissa  |
| \[討論\] 大家覺得新還舊版美女與野獸主題曲好聽？     | 35      | Ga1axyNote7  |
| \[片單\] 關於急救創傷處理的電影                     | 24      | angel5230    |
| \[討論\] 大家聊聊那些原創電影未來可能還會重拍       | 20      | fightclubgf  |
| \[新聞\] 《攻殼機動隊》1995年動畫原版5月攻台        | 6       | CatchPlay    |
| \[Live\] 非法999 21:00 Star Movie                   | 6       | uuuuOPuff    |
| \[LIVE\] 刺激1995 AXN 21:00                         | 48      | pttnowash    |
| Re: \[討論\] 駭客任務重開機？外傳性質發展可能性較高 | 8       | mimi1020b    |
| \[新聞\] 金剛：骷髏島原可能採用的不同結尾及開場     | 9       | ViewMovie    |
| \[請益\] 攻敵必救支線疑問 有雷                      | 5       | jimming      |
| \[好雷\] 遲暮英雄《羅根》最催淚的５個片段           | 8       | cybeth       |
| \[普雷\] 金剛-骷髏島 之大亂鬥                       | 1       | VOT1077      |
| \[討論\] 美女與野獸馬路快閃宣傳與誠實預告           | 3       | kuja         |
| \[普好雷\]最愛你的人是我：廢話少說，快點愛我        | 3       | leo96628     |
| \[好雷\] 這時對 那時錯                              | 5       | takuminauki  |
| \[閒聊\] 昨天是導演盧貝松生日，所以他說……           | 8       | SKnight      |
| Re: \[問片\] 請推薦給問題行為少女看的電影.......    |         | tenshoufly   |
| \[好雷\]當他們認真編織時                            |         | bbtzoe       |
| \[討論\]新舊比一比：真人版《美女與野獸》7大驚喜     | 4       | dennymulan   |
| \[討論\] 葉問3張天志將推出獨立電影                  | 26      | kings5515    |
| \[普雷\]救殭清道夫觀後感                            | 3       | jo87la       |
| \[問片\] 一部日本急診室醫師的電影                   | 17      | sunny0824    |
| \[普雷\] 《限時救援》救人噢！                       | 4       | bestbamboo   |
| \[討論\] 俠盜一號最棒的一場戲(已被砍片)             | 54      | rick0905     |
| \[極負雷\] 美女與野獸-自打巴掌                      | 5       | PttJoke      |
| \[討論\] 從美女與野獸的歷代版本看女性主義           | 8       | iseedeadman  |
| \[問片\] 問一部異形片                               | 7       | IDAY         |
| \[請益\] 攻敵必救的一句台詞                         | 5       | cck525       |
| Re: \[討論\] 從美女與野獸的歷代版本看女性主義       | 64      | caro770880   |
| (本文已被刪除) <groovy>                             | 24      | -            |
| (本文已被刪除) <SODAECHO1>                          | 1       | -            |
| \[問片\] 找一部戰爭急救的片                         | 3       | punpum       |
| \[腥爽雷\]《迎頭重擊》-當全面突襲遇上傑森包恩       | 1       | jk10134      |
| \[討論\] 選看電影會考慮片長嗎？                     | 32      | rs6677       |
| \[討論\] 攻敵必救兩個點請教？                       | 15      | balahaha     |
| \[普好雷\] 美女與野獸 完美重現 長大後的觀後感       | 4       | dunb         |
| \[好雷\]美女與野獸，冰雪終溶                        | 15      | Cause123     |
| \[討論\] "黑塔" The Dark Tower 正式海報發布         | 18      | peter080808  |
| (本文已被刪除) <nightfever>                         | 爆      | -            |
| \[請益\] 問雷 12怒漢結尾（黑白版本）                | 3       | dino23       |
| \[討論\] 看完金剛的心得                             | 6       | achates815   |
| \[翻譯\] 一些你可能不知道將拍續集的電影             | 3       | TVpotato     |
| \[討論\] 駭客任務重開機？外傳性質發展可能性較高     | 17      | jay5566      |
| \[討論\] 《花木蘭》電影不會拍成歌舞片！！！！！     | 爆      | jay5566      |
| (本文已被刪除) \[a122239\]                          |         | -            |
| \[好雷\] 《白蟻：慾望謎網》White Ant 觀後感         | 4       | vul3c9       |
| \[心得\] 教孩子的好片-當他們認真編織時              | 7       | emotorr      |
| \[普好雷\] 美女與野獸                               | 4       | uland26922   |
| \[ 好雷\] 美女與野獸，關鍵字，女巫阿嘉紗            | 12      | kuja         |
| \[請益\] (雷) 攻敵必救 相關問題                     | 7       | singzion333  |
| \[討論\] 為什麼不叫"林祖媽小舞"?                    | 10      | NiNiHOT      |
| \[請益\] 請問守護者聯盟此預告的背景音樂             | 1       | m09963010    |
| (本文已被刪除) \[leo921080931\]                     |         | -            |
| \[好雷\]擁抱燦爛，我們戀愛吧/最後的詩句             | 15      | alexisv41    |
| \[問片\] 電子玩具殺人電影                           | 4       | oldtai       |
| \[微雷\] 健忘村 寓意滿滿耐人尋味                    | 6       | awwooSODA    |
| (本文已被刪除) <marcxxxx>                           | 2       | -            |
| Re: \[好雷\]金剛-景甜這角色是幹嘛的?                | 22      | SQUAD12345   |
| (本文已被刪除) <s2657507>                           | 6       | -            |
| \[普好雷\] 《羅根》遺憾、釋懷、終幕。               | 7       | naestnecniv  |
| (本文已被刪除) <minipig1127>                        | 9       | -            |
| \[討論\] 葉問4正式確定                              | 85      | arsl400      |
| \[好雷\]美女與野獸 真愛打破魔咒                     | 10      | dogwang22    |
| \[好雷\]美女與野獸 - 比動畫版更堅強的貝兒           | 21      | g801109g     |
| \[微雷\]《魔詭》                                    |         | iamnumber121 |

解釋爬蟲結果
------------

``` r
nrow(dataframeAll)
```

    ## [1] 100

總共有100篇文章

``` r
a<-table(dataframeAll$Author)
sort(a)
```

    ## 
    ##       ChloeD  denverkober  ejijo761115     fff15973    fish60233 
    ##            1            1            1            1            1 
    ## freiheitkino    indiasosp     kiwistar       LeedTV      litann4 
    ##            1            1            1            1            1 
    ##  mysmalllamb       r123tw      sarasay     shinbird   Sturmvogel 
    ##            1            1            1            1            1 
    ##    tsukachan      u850234       ueiwei     vm04vm04    angel5230 
    ##            1            1            1            1            1 
    ##    CatchPlay      COCOCCC      Edouard  fightclubgf  Ga1axyNote7 
    ##            1            1            1            1            1 
    ## KingKingCold  lovemelissa     metz1552       mid729      MYLIUUU 
    ##            1            1            1            1            1 
    ##     nasuchan  NCKUFatPork     patdolye ragnarokfans     s2657507 
    ##            1            1            1            1            1 
    ## sampsonlu919     tomgod17       bbtzoe   bestbamboo       cybeth 
    ##            1            1            1            1            1 
    ##   dennymulan      jimming       jo87la    kings5515     leo96628 
    ##            1            1            1            1            1 
    ##    mimi1020b      PttJoke    pttnowash     rick0905      SKnight 
    ##            1            1            1            1            1 
    ##    sunny0824  takuminauki   tenshoufly    uuuuOPuff    ViewMovie 
    ##            1            1            1            1            1 
    ##      VOT1077   achates815     balahaha   caro770880     Cause123 
    ##            1            1            1            1            1 
    ##       cck525       dino23         dunb         IDAY  iseedeadman 
    ##            1            1            1            1            1 
    ##  peter080808       punpum       rs6677     TVpotato    alexisv41 
    ##            1            1            1            1            1 
    ##      arsl400    awwooSODA    dogwang22      emotorr     g801109g 
    ##            1            1            1            1            1 
    ## iamnumber121    m09963010  naestnecniv      NiNiHOT       oldtai 
    ##            1            1            1            1            1 
    ##  singzion333   SQUAD12345   uland26922       vul3c9      jk10134 
    ##            1            1            1            1            2 
    ##         zkow         kuja      jay5566            - 
    ##            2            2            2            8

由上圖可發現，雖然"-"的數量是最多，但是"-"表示是匿名，因此不予考慮；所以文章數最多的作者分別為jay5566、kuja、zkow、jk10134。

dataframeAll這張圖表的資料是在2017/03/20從ptt電影版選出100筆最新文章統計出來的資料。從抓下的結果可以發現大多數人都在討論"美女與野獸"，其次"金剛：骷髏島"，剛好跟上週台北票房的前兩名剛好一樣(<https://tw.movies.yahoo.com/chart.html?cate=taipei>)，因此透過這個例子我們可以從大家發文文章標題的多寡，推論出目前正在熱映中的電影為何。
