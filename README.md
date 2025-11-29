# Renz
<html lang="id">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Maafkan Aku - Julia Aida</title>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    body {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      min-height: 100%;
      font-family: 'Georgia', serif;
      overflow-x: hidden;
    }

    .container {
      width: 100%;
      min-height: 100%;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 40px 20px;
    }

    .apology-card {
      background: #ffffff;
      border-radius: 24px;
      padding: 60px 40px;
      max-width: 600px;
      width: 100%;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .heart-decoration {
      position: absolute;
      font-size: 100px;
      opacity: 0.1;
      animation: float 3s ease-in-out infinite;
    }

    .heart-1 {
      top: -20px;
      left: -20px;
    }

    .heart-2 {
      bottom: -20px;
      right: -20px;
      animation-delay: 1.5s;
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0px) rotate(0deg);
      }
      50% {
        transform: translateY(-20px) rotate(5deg);
      }
    }

    .emoji-large {
      font-size: 80px;
      margin-bottom: 20px;
      animation: pulse 2s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.1);
      }
    }

    h1 {
      font-size: 48px;
      color: #667eea;
      margin: 0 0 10px 0;
      font-weight: bold;
    }

    .recipient {
      font-size: 32px;
      color: #764ba2;
      margin: 0 0 30px 0;
      font-style: italic;
    }

    .message-box {
      background: #f8f9fa;
      border-radius: 16px;
      padding: 30px;
      margin: 30px 0;
      border-left: 4px solid #667eea;
    }

    .message-text {
      font-size: 20px;
      color: #333333;
      line-height: 1.6;
      margin: 0;
    }

    .hearts-row {
      font-size: 32px;
      margin: 30px 0;
      letter-spacing: 10px;
    }

    .closing {
      font-size: 24px;
      color: #764ba2;
      font-weight: bold;
      margin-top: 30px;
    }

    .signature {
      font-size: 18px;
      color: #666666;
      margin-top: 40px;
      font-style: italic;
    }

    @media (max-width: 600px) {
      .apology-card {
        padding: 40px 24px;
      }

      h1 {
        font-size: 36px;
      }

      .recipient {
        font-size: 24px;
      }

      .message-text {
        font-size: 18px;
      }

      .emoji-large {
        font-size: 60px;
      }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body>
  <div class="container">
   <div class="apology-card">
    <div class="heart-decoration heart-1">
     💝
    </div>
    <div class="heart-decoration heart-2">
     💝
    </div>
    <div class="emoji-large">
     😢
    </div>
    <h1 id="main-heading">Maafkan Aku</h1>
    <p class="recipient"><span id="recipient-name">Julia Aida</span> 💕 <span id="nickname">My Bubub</span></p>
    <div class="message-box">
     <p class="message-text" id="apology-message">Maafkan aku ya... Aku tahu aku salah dan aku menyesal. Kamu adalah orang yang paling berharga dalam hidupku. Aku berjanji akan menjadi lebih baik untukmu. 🙏</p>
    </div>
    <div class="hearts-row">
     💝 💖 💝
    </div>
    <p class="closing" id="closing-message">Aku sayang kamu ❤️</p>
    <p class="signature">Dengan tulus dari hati</p>
   </div>
  </div>
  <script>
    const defaultConfig = {
      main_heading: "Maafkan Aku",
      recipient_name: "Julia Aida",
      nickname: "My Bubub",
      apology_message: "Maafkan aku ya... Aku tahu aku salah dan aku menyesal. Kamu adalah orang yang paling berharga dalam hidupku. Aku berjanji akan menjadi lebih baik untukmu. 🙏",
      closing_message: "Aku sayang kamu ❤️",
      background_color: "#667eea",
      secondary_color: "#764ba2",
      text_color: "#333333",
      card_background: "#ffffff",
      font_family: "Georgia"
    };

    async function onConfigChange(config) {
      document.getElementById('main-heading').textContent = config.main_heading || defaultConfig.main_heading;
      document.getElementById('recipient-name').textContent = config.recipient_name || defaultConfig.recipient_name;
      document.getElementById('nickname').textContent = config.nickname || defaultConfig.nickname;
      document.getElementById('apology-message').textContent = config.apology_message || defaultConfig.apology_message;
      document.getElementById('closing-message').textContent = config.closing_message || defaultConfig.closing_message;

      const backgroundColor = config.background_color || defaultConfig.background_color;
      const secondaryColor = config.secondary_color || defaultConfig.secondary_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const cardBackground = config.card_background || defaultConfig.card_background;
      const fontFamily = config.font_family || defaultConfig.font_family;

      document.querySelector('.container').style.background = `linear-gradient(135deg, ${backgroundColor} 0%, ${secondaryColor} 100%)`;
      document.querySelector('h1').style.color = backgroundColor;
      document.querySelector('.recipient').style.color = secondaryColor;
      document.querySelector('.closing').style.color = secondaryColor;
      document.querySelector('.message-box').style.borderLeftColor = backgroundColor;
      document.querySelector('.message-text').style.color = textColor;
      document.querySelector('.apology-card').style.background = cardBackground;
      document.body.style.fontFamily = `${fontFamily}, Georgia, serif`;
    }

    function mapToCapabilities(config) {
      return {
        recolorables: [
          {
            get: () => config.background_color || defaultConfig.background_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.setConfig({ background_color: value });
              }
            }
          },
          {
            get: () => config.secondary_color || defaultConfig.secondary_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.setConfig({ secondary_color: value });
              }
            }
          },
          {
            get: () => config.text_color || defaultConfig.text_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.setConfig({ text_color: value });
              }
            }
          },
          {
            get: () => config.card_background || defaultConfig.card_background,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.setConfig({ card_background: value });
              }
            }
          }
        ],
        borderables: [],
        fontEditable: {
          get: () => config.font_family || defaultConfig.font_family,
          set: (value) => {
            if (window.elementSdk) {
              window.elementSdk.setConfig({ font_family: value });
            }
          }
        },
        fontSizeable: undefined
      };
    }

    function mapToEditPanelValues(config) {
      return new Map([
        ["main_heading", config.main_heading || defaultConfig.main_heading],
        ["recipient_name", config.recipient_name || defaultConfig.recipient_name],
        ["nickname", config.nickname || defaultConfig.nickname],
        ["apology_message", config.apology_message || defaultConfig.apology_message],
        ["closing_message", config.closing_message || defaultConfig.closing_message]
      ]);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a641d2432d7fdf8',t:'MTc2NDQ0MDM3Mi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
