<template>
  <div v-on:scroll="handleScroll">
    <NotificationPanel />
    <header class="header">
      <div class="header-wrapper">
        <img 
          class="header-logo" 
          src="../assets/logo.png" 
          alt="logo">
        <h1>Hello! I'm Achmad Yohni W.F.</h1>
        <h2>Consult, Design, and Develop Websites</h2>
        <p>Have something great in mind? Feels me to contact me.</p>
        <p>I'll help you to make it happen</p>

        <button class="header-btn">LET'S MAKE CONTACT</button>
      </div>
    </header>
    <div class="hl">
      <h1 class="hl-title">How Can I Help You?</h1>
      <div class="hl-sub">
        <p>Our work then targeted, best practices outcomes social innovation synergy.</p>
        <p>Venture philanthropy, revolutionary inclusive policymaker relief. User-centered program areas scale.</p>
      </div>
      <div class="hl-wrapper">
        <HighlightCard 
          v-for="item in highlights" 
          :key="item.name"
          :name="item.name"
          :content="item.content"
          :icon="item.icon"/>
      </div>
    </div>
    <footer class="footer">
      &copy; 2020 Yohni. All rights reserved.​
    </footer>
    <NewLetter 
      @close-click="closeNL"
      class="nl"
      :class='NLshow=="two" ? "nl-show" : ""'/>
  </div>
</template>

<script>
import NotificationPanel from '../components/NotificationPanel';
import HighlightCard from '../components/HighlightCard';
import NewLetter from '../components/NewsLetter';

export default {
  name: 'home',
  components: {
    NotificationPanel,
    HighlightCard,
    NewLetter,
  },
  data() {
    return {
      scroolH: 0,
      NLshow: 'one',
      highlights: [
        {
          name: 'Consult',
          content: 'Co-create, design thinking; strengthen infrastructure resist granular. Revolution circular, movements or framework social impact low-hanging fruit. Save the world compelling revolutionary progress.',
          icon: 'ic_chat',
        },
        {
          name: 'Design',
          content: 'Policymaker collaborates collective impact humanitarian shared value vocabulary inspire issue outcomes agile. Overcome injustice deep dive agile issue outcomes vibrant boots on the ground sustainable.',
          icon: 'ic_brush',
        },
        {
          name: 'Develop',
          content: 'Revolutionary circular, movements a or impact framework social impact low-hanging. Save the compelling revolutionary inspire progress. Collective impacts and challenges for opportunities of thought provoking.',
          icon: 'ic_development',
        },
        {
          name: 'Marketing',
          content: 'Peaceful; vibrant paradigm, collaborative cities. Shared vocabulary agile, replicable, effective altruism youth. Mobilize commitment to overcome injustice resilient, uplift social transparent effective.',
          icon: 'ic_speaker',
        },
        {
          name: 'Manage',
          content: 'Change-makers innovation or shared unit of analysis. Overcome injustice outcomes strategize vibrant boots on the ground sustainable. Optimism, effective altruism invest optimism corporate social.',
          icon: 'ic_partner',
        },
        {
          name: 'Evolve',
          content: 'Activate catalyze and impact contextualize humanitarian. Unit of analysis overcome injustice storytelling altruism. Thought leadership mass incarceration. Outcomes big data, fairness, social game-changer.',
          icon: 'ic_increase',
        },
      ],
    };
  },
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 0.3 * window.innerHeight) {
        this.scroolH += 1;
      }

      if (this.scroolH >= 1 && this.NLshow === 'one') {
        this.NLshow = 'two';
      }
    },
    closeNL() {
      this.NLshow = 'three';
      console.log(this.NLshow);
    },
  },
};

</script>

<style lang="scss">
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
  line-height: 1;
  background: #e5e5e5;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
a {
  text-decoration: none;
  color: blue;
}
button {
  outline: none;
  border: none;
  cursor: pointer;
}

@import '../styles/theme.scss';

.header{
  background: url('../assets/header_bg.jpg');
  background-size: cover;
  position: relative;

  .header-wrapper{
    background: rgba($color: $MyDarkBlue, $alpha: 0.5);
    min-height: 568px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    color: #ffffff;
    text-align: center;
    padding: 0 24px;

    .header-logo{
      position: absolute;
      top: 24px;
      left: 24px;
      width: 64px;
      height: 64px;

      @media (max-width: 320px) {
        width: 40px;
        height: 40px;
        top: 12px;
      }
    }

    h1{
      font-weight: 400;
      font-size: 32px;
      margin-bottom: 12px;
    }

    h2{
      font-weight: 600;
      font-size: 24px;
      margin-bottom: 12px;
    }

    p{
      margin-bottom: 4px;
    }

    button.header-btn{
      margin-top: 24px;
      padding: 12px 24px;
      background: rgba($color: #ffffff, $alpha: 0);
      border: #ffffff solid 2px;
      color: #ffffff;
      font-weight: bold;
      transition: all 0.25s;

      &:hover{
        color: $MyBlue;
        background: rgba($color: #ffffff, $alpha: 1);
      }
    }
  }
}

.hl{
  padding: 24px;
  margin-bottom: 48px;

  .hl-title{
    text-align: center;
    margin-top: 24px;
    margin-bottom: 24px;
    font-weight: 400;
    font-size: 32px;
  }

  .hl-sub{
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    line-height: 140%;
    margin-bottom: 24px;

    @media (min-width: 480px) {
      p{
        max-width: 40%;
      }  
    }
  }

  .hl-wrapper{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }
}

.footer{
  padding: 48px 12px;
  background-color: $MyDarkBlue;
  color: #f1f1f1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.nl{
  transform: translateY(400px);
  transition: all 0.5s ease-in;


}

.nl-show{
  transform: translateY(0);
}


</style>