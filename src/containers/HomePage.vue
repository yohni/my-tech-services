<template>
  <div>
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
        <p>Venture philanthropy, revolutionary inclusive policymaker relief. User-centered
program areas scale.</p>
      </div>
      <div class="hl-wrapper">
        <div class="hl-item">
          <div class="hl-item-header">
            <div class="hl-item-title">
              
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NotificationPanel from '../components/NotificationPanel';

export default {
  name: 'home',
  components: {
    NotificationPanel,
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

@import '../styles/theme';

.header{
  background: url('../assets/header_bg.jpg');
  background-size: cover;
  position: relative;

  .header-wrapper{
    background: rgba($color: #004a75, $alpha: 0.5);
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
}

</style>