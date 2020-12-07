<template>
  <div id="app">
    <div class="title-row">
      <h1 style="font-size: 36px">王凯</h1>
      <div style="padding-left: 48px; font-size: 24px">
        四年工作经验 | 本科 | 前端开发工程师
      </div>
    </div>

    <div class="sm-title">基本信息</div>
    <div class="base-info">
      <div class="base-info-left">
        <div class="base-info-item">姓名：王凯</div>
        <div class="base-info-item">年龄：27</div>
        <div class="base-info-item">电话：15652912603</div>
        <div class="base-info-item">学校：华北电力大学（北京）2016 年 7 月毕业</div>
        <div class="base-info-item">
          个人博客：<a
            target="_blank"
            href="http://www.jianshu.com/u/d184d3ab9060"
            >http://www.jianshu.com/u/d184d3ab9060</a
          >
        </div>
      </div>
      <div class="base-info-right">
        <div class="base-info-item">性别：男</div>
        <div class="base-info-item">邮箱：waka931124@163.com</div>
        <div class="base-info-item">专业：软件工程</div>
        <div class="base-info-item">
          GitHub：<a href="https://github.com/badwaka" target="_blank"
            >https://github.com/badwaka</a
          >
        </div>
      </div>
    </div>

    <div class="sm-title">个人技能</div>
    <ul class="skill">
      <li
        v-for="(skill, skillIndex) in skills"
        :key="'skill' + skillIndex"
        class="skill-item"
      >
        <div class="point"></div>
        {{ skill }}
      </li>
    </ul>

    <div class="sm-title">自我评价</div>
    <ul class="skill">
      <li
        v-for="(selfAssessment, selfAssessmentIndex) in selfAssessments"
        :key="'selfAssessment' + selfAssessmentIndex"
        class="skill-item"
      >
        <div class="point"></div>
        {{ selfAssessment }}
      </li>
    </ul>

    <div class="sm-title">工作经验</div>
    <section
      v-for="(experience, experienceIndex) in experiences"
      :key="'experience' + experienceIndex"
    >
      <div style="margin-top: 10px" class="row">
        <div class="company-name">
          {{ experience.company }} | {{ experience.job }} |
          {{ experience.city }}
        </div>
        <div>{{ experience.beginTime }} - {{ experience.endTime }}</div>
      </div>

      <div
        v-for="(project, projectIndex) in experience.projects"
        :key="'project' + projectIndex"
      >
        <div class="skill-item">
          <div class="point"></div>
          <span style="margin-right: 10px">{{ project.name }}</span>
          <a :href="project.link" target="_blank">{{ project.link }}</a>
        </div>
        <ul
          v-for="(intro, introIndex) in project.intros"
          :key="'intro' + introIndex"
        >
          <li class="intro-item">
            <div class="point-square"></div>
            {{ intro }}
          </li>
        </ul>
      </div>
    </section>

    <div class="sm-title">个人项目</div>
    <section
      v-for="(project, projectIndex) in personalProjects"
      :key="'personalProject' + projectIndex"
    >
      <div class="skill-item">
        <div class="point"></div>
        <span style="margin-right: 10px">{{ project.name }}</span>
        <a :href="project.link" target="_blank">{{ project.link }}</a>
      </div>
      <ul
        v-for="(intro, introIndex) in project.intros"
        :key="'personalIntro' + introIndex"
      >
        <li class="intro-item">
          <div class="point-square"></div>
          {{ intro }}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      skills: [
        "掌握 HTML、CSS、JS，熟悉 ES6，熟练使用 TypeScript",
        "熟悉 Sass、Less，了解 Stylus、PostCSS",
        "掌握 Vue、React、Redux，熟悉微信小程序、AppCan.js (类 Ionic 的 Hybrid 框架)，了解 React Native",
        "熟练使用 Atom、San 等类 Vue 百度自研框架",
        "熟练使用 Webpack、Gulp；熟悉前端工程化和组件化开发思想",
        "有后端开发经历，熟练使用 Node、Express、Koa，了解 MySQL，MongoDB",
        "熟练使用 npm，了解 Yarn",
        "有 Android 原生开发经历，熟悉 Java、Android SDK 及 Android 调试工具",
        "日常开发使用 macOS，WebStorm/VSCode，熟悉 Git，熟练使用 Linux 命令",
      ],
      selfAssessments: [
        "有自己的技术博客，80 余篇原创博客，乐于分享，热爱新技术",
        "关注开源技术，技术视野开阔，学习能力强，能快速上手新技术，同时也能快速熟悉业务",
        "211 大学软件工程专业毕业，计算机基础扎实",
        "理解前端工程化思想，对构建和持续集成有一定认识",
        "理解组件化开发思想，有一定的设计和抽象能力，独立编写可复用的 React 组件及 Node 中间件",
        "对后端技术和数据库有一定了解",
        "熟悉 Android 原生技术，在移动端适配及原生能力开发调试有优势",
      ],
      experiences: [
        {
          company: "百度在线网络技术（北京）有限公司",
          job: "前端资深研发工程师 | 职级 T6 | 2019 年度绩效 E",
          city: "北京",
          beginTime: "2017-09-13",
          endTime: "至今",
          contents: [],
          projects: [
            {
              name: "搜索前端通用组件 Topic 技术负责人",
              intros: [
                "search-ui 通用组件库，影响 pv 125亿+，20+ 参与开发，影响公司自然模板、六合、视频、图搜、时效性、百科等 20+ 产品",
                "lego && 无极项目搜索 C 端组件、卡片迁移负责人，影响 pv 2.2 亿+，74+ 参与开发，覆盖金融、音乐、服务、民生、家装等 20+ 垂类业务",
                "pmd.css 搜索通用样式库、iconfont 搜索通用图标库负责人，影响整个百度搜索的展现",
                "Mars UI 小程序组件库负责人，已接入汽车（度寻车）、招聘（百度百聘）、金融（百股精）、法律（豌豆律师）、医疗（医疗健康中心）、家装（装馨家） 6+ 小程序",
              ],
            },
            {
              name: "LEGO 搜索智能卡片机制",
              intros: [
                "实现通用卡片机制，具备可配置的能力，进一步降低视觉/交互的整体升级的成本",
                "设计了组件的引入标准和流程，负责 lego C 端组件库的开发、迭代及维护",
                "负责 lego 卡片的开发至上线全流程开发指导、文档编写、问题答疑及上线值周",
                "负责 json mirror 文件编译器，拓展配置文件语法；及编译、上线优化等工程效率任务",
                "负责开发 lego 卡片统计脚本及工具",
              ],
            },
            {
              name: "搜索全局样式迭代",
              intros: [
                "负责搜索全局样式 pmd.css、搜索通用图标库 iconfont 的开发迭代及维护",
                "负责 NA 2.0 高级感项目、搜索 D20 样式改版项目、搜索暗黑模式、oppo 负一屏等重点项目的开发和上线",
                "推动流程规范建设，推动 UE 对图标进行分类和去重，提高开发人员的效率，减少通用图标库的体积；获得 2019年 Q4 蓝军小赞荣誉",
              ],
            },
            {
              name: "商品、医疗、金融、旅游等搜索阿拉丁垂类",
              intros: [
                "负责垂类相关项目的需求评审、迭代及体验优化，不断满足新的业务方向上的产品需求",
                "能够做出完整开发设计方案，对接PM、UE、RD推进项目落地，负责指导新人完成开发任务，解决问题",
                "负责医疗专家问诊、肺炎疫情地图、商品熊掌号、百股精金融小程序等重点项目的开发维护任务",
              ],
            },
          ],
        },
        {
          company: "北京云莱坞文化传媒有限公司",
          job: "前端开发工程师",
          city: "北京",
          beginTime: "2017.03.27",
          endTime: "2017.08.28",
          contents: [
            "1. 负责公司产品、项目的 web 前端开发及移动端开发和维护；",
            "2. 运用 HTML、CSS 将设计图转化为静态页面，运用 JS 及相关库实现交互效果开发；",
            "3. 根据用户要求与项目需求解决所需浏览器兼容性问题以及 BUG；",
            "4. 利用 AJAX 与后端配合，进行数据逻辑的走通，完成数据交互、动态信息展现；",
            "5. 在公司内部进行前端技术分享；",
          ],
          projects: [
            {
              name: "云莱坞作家后台",
              link: "http://user.yunlaiwu.com/",
              intros: [
                "负责整个作家后台的功能开发及维护，负责 SPA 基础工程的搭建与优化；",
                "在 Node 层使用 ejs 渲染页面，进行接口转发解决上传文件跨域的问题",
                "我在完善功能样式后重构整个项目：使用 AntD 替代 react-bootstrap 重写样式，编写特殊组件完成需求并抽象出公共 UI 库",
                "升级 webpack 及去除无用依赖库，重新配置基础构建工程，使编译打包后的文件大小缩减至 30%；抽象出第三方依赖库作为 vendor 增强缓存策略",
              ],
            },
            {
              name: "云莱坞官方网站",
              link: "http://www.yunlaiwu.com/",
              intros: [
                "主要负责 PC 端登录注册、闪电征稿、个人主页等模块，H5 端版权交易周、投票运营页等前端页面，及 node 中间层的开发与维护；",
                "在详情页及列表页通过 Node 层 SSR 渲染首屏数据增强 SEO；使用百度统计、美洽等第三方工具统计流量和实现客服功能",
                "重构整个 Node 层代码，通过 UA 判断请求，手动代理移动端流量至另一机器集群进行流量压力分流；",
                "独立使用 LeanCloudAPI、微信 API，不依赖后端，开发完整的投票功能（PC 结果页、微信端投票页）",
              ],
            },
          ],
        },
        {
          company: "【实习，16 年 7 月转正】正益移动互联科技股份有限公司（AppCan）",
          job: "前端开发工程师",
          city: "北京",
          beginTime: "2015.10",
          endTime: "2017.03.24",
          contents: [
            "1. 负责公司产品、项目的 web 前端开发及移动端开发和维护；",
            "2. 运用 HTML、CSS 将设计图转化为静态页面，运用 JS 及相关库实现交互效果开发；",
            "3. 根据用户要求与项目需求解决所需浏览器兼容性问题以及 BUG；",
            "4. 利用 AJAX 与后端配合，进行数据逻辑的走通，完成数据交互、动态信息展现；",
            "5. 负责公司部分 Android 原生端插件的开发和维护；",
            "6. 负责公司项目的前端及 Android 原生端技术支持；",
            "7. 在公司内部进行前端技术分享；",
            "8. 负责维护公司论坛 AppCan 社区，并进行一些技术方面的答疑。",
          ],
          projects: [
            {
              name: "正益工作 Hybrid App",
              link: "http://work.zyhao.com/",
              intros: [
                "负责正益工作移动端 App 功能门户、IM 会话、企业通讯录、考勤签到、工单任务报告等模块的功能开发及维护；",
                "该项目门户模块源代码已被中国电建、上海卡斯柯、万科集团、福田汽车、奥凯航空等企业级用户所采用；",
                "我在完善功能样式后使用 Vue.js 重构部分项目；使用 Sass 和 flex 布局重写 UI，代码量减少 20%",
              ],
            },
            {
              name: "正益移动 - 微信小程序",
              intros: [
                "负责全部前端页面的设计、界面实现及功能实现；负责小程序的接入和上线发布；",
                "使用微信小程序框架 MINA，及微信官方样式库 WeUI 实现前端界面；配合后端实现小程序登录流程，并完成前后端接口的联调对接工作。",
              ],
            },
            {
              name: "乌鲁木齐银行-雪莲伙伴",
              link: "http://www.uccb.com.cn/phone.aspx",
              intros: [
                "负责AppCan框架前端性能优化及Android原生插件开发的技术支持；",
                "因为同时懂得前端技术和Android原生技术，将原本需要两个人的任务一个人完成，并将工时缩短至一半；",
              ],
            },
            {
              name: "中国电力建设集团-电建通",
              link: "http://pcm.powerchina.cn/",
              intros: [
                "根据华为提供的 eSpaceSDK，负责 Android 原生模块 Voip 语音通话的二次开发、封装和性能优化；",
                "大量使用 Broadcast 广播接收器和 Handler 多线程编程，为 JS 端提供 Voip 语音通话功能；",
                "开发期间由于文档、SDK 设计问题，与华为技术人员进行大量邮件、电话沟通，将语音通话功能如期上线",
              ],
            },
            {
              name: "企业级项目 Android 插件开发",
              intros: [
                "杭州指端项目 开发 Android 计步器模块，实现多传感器计步，数据库缓存数据及前台服务；",
                "绫致服装项目 开发 Android 图片标签模块，实现给图片添加标签、编辑、移动的功能；",
                "正益工作项目 开发 Android 照相机模块，实现自定义Android照相机；",
                "协同开发项目 开发悬浮窗原生 View，并实现上传崩溃日志和 log 功能；",
                "百年人寿项目 根据 mupdf，二次开发 Android PDF 解析器模块；",
                "江苏烟草项目 开发 Android NFC 读取模块；",
              ],
            },
          ],
        },
        {
          company: "【实习】北京观天智创科技有限公司",
          job: "Android 开发工程师",
          city: "北京",
          beginTime: "2015.03",
          endTime: "2015.09",
          projects: [
            //                        {
            //                            name: '旺铺帮平板点餐',
            //                            intros: [
            //                                '1. 该项目是面向餐馆顾客的一款平板点餐App，主要功能有用户点餐、管理员设置菜单；',
            //                                '2. 负责用户登录模块和用户点餐模块的功能开发及维护；',
            //                                '3. 使用Android布局实现复杂页面；使用Framework分割UI视图；使用HttpClient进行网络请求并使用handler异步更新UI。'
            //                            ]
            //                        },
            {
              name: "旺铺帮掌柜宝",
              link: "http://www.wangpupos.com/serve/twodownload.html",
              intros: [
                "负责该项目 Android 客户端，店铺进销管理、营业流水管理模块的开发及维护；",
                "根据需求文档，使用 Android 各种布局实现页面，使用 Handler 和多线程技术请求网络并异步更新 UI；",
                "自定义 View 实现简单的条形图。",
              ],
            },
            {
              name: "我们去哪儿",
              link:
                "http://sj.qq.com/myapp/detail.htm?apkName=com.travel.travel_app",
              intros: [
                "负责该项目的 Android 客户端功能开发及维护；",
                "根据产品需求，使用 android 布局和各类控件实现各种复杂界面；",
                "使用内置 SQLite 数据库存取数据；使用 JUnit 进行单元测试。",
              ],
            },
          ],
        },
      ],
      personalProjects: [
        {
          name: "个人博客",
          link: "https://github.com/badwaka/blog-waka-by-vue",
          intros: [
            "个人博客全栈作品。遵循前端工程化和组件化思想,",
            "使用Vue2+ES6+MuseUI编写前端代码，使用Sass+PostCSS编写页面样式,使用webpack编译打包，",
            "使用Express+MongoDB搭建后台服务，并独立完成linux环境的服务器部署",
          ],
        },
        {
          name: "gallery-by-react-waka",
          link: "https://github.com/badwaka/gallery-by-react-waka",
          intros: ["React+webpack实现的画廊程序"],
        },
        {
          name: "lottery-by-vue",
          link: "https://github.com/badwaka/lottery-by-vue",
          intros: ["Vue.js+Materialize实现的简单的抽奖程序"],
        },
        {
          name: "WakaPedometer",
          link: "https://github.com/badwaka/WakaPedometer",
          intros: ["Android原生计步器程序，使用开源库Volley、fastjson"],
        },
        {
          name: "SmallDianPing",
          link: "https://github.com/badwaka/SmallDianPing",
          intros: ["Android原生仿美团订餐程序，使用高德地图SDK"],
        },
      ],
    };
  },
};
</script>

<style>
@import url(css/reset.css);
@import url(css/resume.css);
#app {
  padding: 40px;
}
</style>
