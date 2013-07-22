har-tools
=========

tools for HAR file

harx : extract files from HAR file. Domain name and all fold info are kept.


harx
--------

Usage: harx [options] har-file

    -l                  List files , lead by [index]
    -lp urlPattern      like -l , but filter with urlPattern
    -a dir              extract All content to [dir]
    -i Index            extract the [index] content , need run with -l first to get [index]
    -p urlPattern dir   like -a , but filter with urlPattern

Examples
--------

Step1: Save HAR.

    - open Chrome browser ;
    - open Develeper Tools, switch to Network panel;
    - enter website url, you will see all requests in Network panel;
    - Right Click in Network panel, choose "Save as HAR with Content", that's all.

Step2: Explor content in HAR

    - harx -l /tmp/site.har

    You will get something like this:

        mac:har-tools tony$ harx -l /tmp/google.har 
        [  0][   GET][                text/html][Size:    3247][URL:http://www.google.cn/]
        [  1][   GET][                image/png][Size:    7842][URL:http://www.google.cn/landing/cnexp/google-search.png]
        [  2][   GET][                text/html][Size:     962][URL:http://www.google.cn/intl/zh-CN_cn/images/cn_icp.gif]
        [  3][   GET][                image/png][Size:    1165][URL:chrome-extension://pioclpoplcdbaefihamjohnefbikjilc/images/nudge-icons/nudge-icon-arrow-up.png]
        [  4][   GET][                image/png][Size:    1171][URL:chrome-extension://pioclpoplcdbaefihamjohnefbikjilc/images/nudge-icons/nudge-icon-arrow-down.png]
        [  5][   GET][                image/png][Size:    1236][URL:chrome-extension://pioclpoplcdbaefihamjohnefbikjilc/images/nudge-icons/nudge-icon-arrow-lr.png]
        [  6][   GET][                image/png][Size:    1193][URL:chrome-extension://pioclpoplcdbaefihamjohnefbikjilc/images/nudge-icons/nudge-icon-return.png]
        [  7][   GET][                 text/css][Size:     131][URL:chrome-extension://pioclpoplcdbaefihamjohnefbikjilc/css/searchhelper.css]
        [  8][   GET][                 text/css][Size:    2806][URL:chrome-extension://cpngackimfmofbokmjmljamhdncknpmg/style.css]
        [  9][   GET][          text/javascript][Size:   10754][URL:chrome-extension://cpngackimfmofbokmjmljamhdncknpmg/page_context.js]

Step3: Extract them all.

    - harx -a /tmp/some_dir /tmp/site.har

    Now you can jump into that folder to see what you get .


Resources
---------

- [HAR 1.2 Spec][1]
- [HAR Viewer][2]

[1]: http://www.softwareishard.com/blog/har-12-spec/
[2]: http://www.softwareishard.com/blog/har-viewer/