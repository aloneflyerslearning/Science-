<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>कक्षा 10 विज्ञान प्रश्नोत्तरी</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 20px;
            color: #333;
        }
        h1 {
            text-align: center;
            color: #0056b3;
            margin-bottom: 30px;
        }
        #section-selector {
           text-align: center;
            margin-bottom: 20px;
        }
      #section-selector label{
            margin-right: 10px;
        }
        .section {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            padding: 20px;
            margin-bottom: 20px;
            display: none; /* Hide initially */
        }
        .section.active {
            display: block;
        }
         .section h2 {
            color: #0056b3;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }
        .question {
            margin-bottom: 15px;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 4px;
        }
        .question p {
          font-weight: bold;
        }
        .answer-options label {
            display: block;
            margin-bottom: 8px;
            cursor: pointer;
            padding: 8px;
            border-radius: 4px;
            transition: background-color 0.3s ease;
        }
       .answer-options label:hover {
            background-color: #f0f0f0;
       }
       .answer-options label input[type="radio"]{
            margin-right: 8px;
           vertical-align: middle;
       }
         #results {
            margin-top: 30px;
            border: 1px solid #ddd;
            padding: 20px;
             border-radius: 8px;
            background-color: #fff;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: none;
        }
        #results h2 {
            color: #0056b3;
        }
        #results p {
            margin-bottom: 10px;
        }
        .correct {
            color: green;
            font-weight: bold;
        }
        .incorrect {
            color: red;
            font-weight: bold;
        }
        button[type="submit"] {
           background-color: #0056b3;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
             display: block;
            margin: 20px auto;
             transition: background-color 0.3s ease;
        }
         button[type="submit"]:hover{
            background-color: #004284;
        }
    </style>
</head>
<body>

    <h1>कक्षा 10 विज्ञान प्रश्नोत्तरी</h1>

    <div id="section-selector">
        <label><input type="radio" name="quiz-section" value="0">खंड 1</label>
        <label><input type="radio" name="quiz-section" value="1">खंड 2</label>
        <label><input type="radio" name="quiz-section" value="2">खंड 3</label>
        <label><input type="radio" name="quiz-section" value="3">खंड 4</label>

    </div>

    <div id="quiz-container">
        <!--  Sections will be dynamically loaded here using JavaScript -->
    </div>

    <div id="results">
        <h2>परिणाम</h2>
        <p>आपका स्कोर: <span id="score"></span>/100</p>
        <div id="feedback"></div>
    </div>

    <script>
       const quizData = [
      {
        section: "खंड 1: रासायनिक अभिक्रियाएँ एवं समीकरण तथा अम्ल, क्षारक एवं लवण",
        questions: [
        {
          question: "रासायनिक समीकरण में अभिकारकों और उत्पादों को किन प्रतीकों से दर्शाया जाता है?",
          options: ["सूत्रों द्वारा", "तत्वों के नामों द्वारा", "प्रतीकों द्वारा", "शब्दों द्वारा"],
          answer: "प्रतीकों द्वारा",
        },
          {
          question: "जब कोई धातु अम्ल के साथ अभिक्रिया करती है, तो कौनसी गैस उत्सर्जित होती है?",
          options: ["ऑक्सीजन", "हाइड्रोजन", "नाइट्रोजन", "कार्बन डाइऑक्साइड"],
          answer: "हाइड्रोजन",
        },
          {
          question: "वह अभिक्रिया जिसमें दो या दो से अधिक पदार्थ मिलकर एक नया पदार्थ बनाते हैं, कहलाती है?",
          options: ["विस्थापन अभिक्रिया", "वियोजन अभिक्रिया", "संयोजन अभिक्रिया", "अपघटन अभिक्रिया"],
          answer: "संयोजन अभिक्रिया",
        },
         {
          question: "निम्न में से कौन-सी रासायनिक अभिक्रिया में ऊष्मा का उत्सर्जन होता है?",
          options: ["ऊष्माशोषी अभिक्रिया", "ऊष्माक्षेपी अभिक्रिया", "उदासीनीकरण अभिक्रिया", "अपघटन अभिक्रिया"],
          answer: "ऊष्माक्षेपी अभिक्रिया",
        },
          {
          question: "CaCO<sub>3</sub> → CaO + CO<sub>2</sub> किस प्रकार की अभिक्रिया है?",
          options: ["संयोजन अभिक्रिया", "वियोजन अभिक्रिया", "विस्थापन अभिक्रिया", "द्विविस्थापन अभिक्रिया"],
          answer: "वियोजन अभिक्रिया",
        },
        {
          question: "लोहे में जंग लगना किस प्रकार की अभिक्रिया का उदाहरण है?",
          options: ["उदासीनीकरण", "अपघटन", "संक्षारण", "ऑक्सीकरण"],
          answer: "संक्षारण",
        },
          {
          question: "वह पदार्थ जो रासायनिक अभिक्रिया में भाग लेते हैं, कहलाते हैं?",
          options: ["उत्पाद", "अभिकारक", "उत्प्रेरक", "विलयन"],
          answer: "अभिकारक",
        },
         {
            question: "रासायनिक समीकरण को संतुलित करना क्यों आवश्यक है?",
            options: ["रासायनिक अभिक्रिया की गति बढ़ाने के लिए", "द्रव्यमान संरक्षण के नियम का पालन करने के लिए", "अभिक्रिया को ऊष्माक्षेपी बनाने के लिए", "अभिक्रिया को रंगीन बनाने के लिए"],
            answer: "द्रव्यमान संरक्षण के नियम का पालन करने के लिए",
        },
        {
          question: "वह अभिक्रिया जिसमें एक पदार्थ दो या दो से अधिक सरल पदार्थों में टूट जाता है, कहलाती है?",
          options: ["संयोजन अभिक्रिया", "विस्थापन अभिक्रिया", "अपघटन अभिक्रिया", "उदासीनीकरण अभिक्रिया"],
          answer: "अपघटन अभिक्रिया",
        },
         {
          question: "प्रकाश रासायनिक अभिक्रियाओं में, किस ऊर्जा का उपयोग किया जाता है?",
          options: ["ऊष्मीय ऊर्जा", "प्रकाश ऊर्जा", "यांत्रिक ऊर्जा", "विद्युत ऊर्जा"],
          answer: "प्रकाश ऊर्जा",
        },
        {
          question: "निम्नलिखित में से कौन एक रेडॉक्स अभिक्रिया का उदाहरण है?",
          options: ["उदासीनीकरण अभिक्रिया", "संयोजन अभिक्रिया", "अपघटन अभिक्रिया", "संक्षारण अभिक्रिया"],
          answer: "संक्षारण अभिक्रिया",
        },
         {
          question: "रासायनिक अभिक्रियाओं में, उत्प्रेरक का क्या कार्य होता है?",
          options: ["अभिक्रिया को धीमा करना", "अभिक्रिया को तेज करना", "अभिक्रिया की सांद्रता बढ़ाना", "अभिक्रिया का रंग बदलना"],
          answer: "अभिक्रिया को तेज करना",
        },
        {
          question: "जब किसी पदार्थ का ऑक्सीकरण होता है, तो क्या होता है?",
          options: ["इलेक्ट्रॉन ग्रहण करता है", "इलेक्ट्रॉन खोता है", "प्रोटॉन ग्रहण करता है", "प्रोटॉन खोता है"],
          answer: "इलेक्ट्रॉन खोता है",
        },
         {
            question: "निम्नलिखित में से कौन सा एक ऊष्माशोषी अभिक्रिया का उदाहरण है?",
             options: ["जलना", "श्वसन", "प्रकाश संश्लेषण", "लोहे पर जंग लगना"],
            answer: "प्रकाश संश्लेषण",
        },
        {
          question: "किस प्रकार की अभिक्रिया में दो यौगिक अपने आयनों का आदान-प्रदान करते हैं?",
            options: ["संयोजन अभिक्रिया", "वियोजन अभिक्रिया", "विस्थापन अभिक्रिया", "द्विविस्थापन अभिक्रिया"],
            answer: "द्विविस्थापन अभिक्रिया",
        },
        {
           question: "सिल्वर क्लोराइड सूर्य के प्रकाश में किस रंग में बदल जाता है?",
             options: ["काला", "सफेद", "पीला", "हरा"],
            answer: "काला",
        },
        {
          question: "निम्न में से कौन सा एक रासायनिक परिवर्तन का उदाहरण है?",
            options: ["बर्फ का पिघलना", "पानी का उबलना", "कागज का जलना", "नमक का पानी में घुलना"],
             answer: "कागज का जलना",
         },
        {
          question: "CuO + H<sub>2</sub> → Cu + H<sub>2</sub>O किस प्रकार की अभिक्रिया है?",
           options: ["संयोजन अभिक्रिया", "वियोजन अभिक्रिया", "रेडॉक्स अभिक्रिया", "विस्थापन अभिक्रिया"],
             answer: "रेडॉक्स अभिक्रिया",
       },
         {
             question: "वह अभिक्रिया जिसमें अपचयन और उपचयन एक साथ होते हैं, कहलाती है?",
            options: ["उदासीनीकरण अभिक्रिया", "विस्थापन अभिक्रिया", "रेडॉक्स अभिक्रिया", "संयोजन अभिक्रिया"],
             answer: "रेडॉक्स अभिक्रिया",
         },
        {
           question: "रासायनिक अभिक्रियाओं के फलस्वरूप प्राप्त होने वाले पदार्थ कहलाते हैं?",
           options: ["अभिकारक", "उत्पाद", "उत्प्रेरक", "मिश्रण"],
           answer: "उत्पाद",
       },
        {
          question: "अम्ल स्वाद में कैसे होते हैं?",
          options: ["मीठा", "खारा", "खट्टा", "कड़वा"],
          answer: "खट्टा",
        },
          {
            question: "क्षारक स्वाद में कैसे होते हैं?",
           options: ["मीठा", "खट्टा", "नमकीन", "कड़वा"],
            answer: "कड़वा",
        },
        {
          question: "नीले लिटमस पत्र को लाल कौन करता है?",
           options: ["क्षार", "लवण", "अम्ल", "उदासीन विलयन"],
          answer: "अम्ल",
        },
         {
          question: "लाल लिटमस पत्र को नीला कौन करता है?",
            options: ["अम्ल", "लवण", "क्षार", "उदासीन विलयन"],
          answer: "क्षार",
        },
        {
          question: "pH स्केल में 7 से कम मान वाले विलयन क्या होते हैं?",
            options: ["क्षारीय", "उदासीन", "अम्लीय", "लवण"],
          answer: "अम्लीय",
        },
        ],
      },
        {
        section: "खंड 2: धातु एवं अधातु",
        questions: [
         {
          question: "निम्नलिखित में से कौन सी धातु सबसे अधिक प्रतिक्रियाशील है?",
          options: ["लोहा", "सोना", "पोटैशियम", "एल्यूमीनियम"],
          answer: "पोटैशियम",
        },
          {
            question: "कौन सी धातु कमरे के तापमान पर द्रव अवस्था में पाई जाती है?",
           options: ["पारा", "सोना", "चाँदी", "एल्युमीनियम"],
            answer: "पारा",
        },
        {
          question: "निम्नलिखित में से कौन सी अधातु विद्युत की सुचालक है?",
           options: ["सल्फर", "ग्रेफाइट", "ऑक्सीजन", "फास्फोरस"],
          answer: "ग्रेफाइट",
        },
         {
          question: "धातुओं का वह गुण जिसके कारण उन्हें पीटकर पतली चादरों में बदला जा सकता है, कहलाता है?",
            options: ["आघातवर्ध्यता", "तन्यता", "चालकता", "कठोरता"],
          answer: "आघातवर्ध्यता",
        },
        {
          question: "धातुओं का वह गुण जिसके कारण उन्हें खींचकर तारों में बदला जा सकता है, कहलाता है?",
            options: ["आघातवर्ध्यता", "तन्यता", "चालकता", "कठोरता"],
          answer: "तन्यता",
        },
        {
          question: "सोडियम धातु को किस में डुबो कर रखा जाता है?",
           options: ["पानी", "तेल", "ग्लिसरीन", "पेट्रोल"],
          answer: "तेल",
         },
         {
           question: "सबसे हल्की धातु कौन सी है?",
            options: ["लिथियम", "एल्युमीनियम", "सोडियम", "पोटैशियम"],
            answer: "लिथियम",
        },
         {
          question: "निम्नलिखित में से कौन सा एक उपधातु है?",
           options: ["सोना", "चाँदी", "सिलिकॉन", "एल्युमीनियम"],
           answer: "सिलिकॉन",
        },
        {
          question: "लोहे पर जिंक की परत चढ़ाने की प्रक्रिया क्या कहलाती है?",
           options: ["संक्षारण", "यसदलेपन", "विद्युतलेपन", "मिश्रधातु बनाना"],
           answer: "यसदलेपन",
       },
       {
           question: "कॉपर सल्फेट के विलयन में लोहे की कील डालने पर क्या होगा?",
             options: ["कोई प्रतिक्रिया नहीं होगी", "कॉपर जमा होगा", "लोहा जमा होगा", "विलयन का रंग बदल जाएगा"],
           answer: "कॉपर जमा होगा",
        },
        {
            question: "सबसे कठोर धातु कौन सी है?",
           options: ["टंगस्टन", "लोहा", "सोना", "प्लेटिनम"],
           answer: "टंगस्टन",
        },
         {
           question: "अम्लों के साथ धातुएं अभिक्रिया करके कौन सी गैस बनाती हैं?",
           options: ["ऑक्सीजन", "नाइट्रोजन", "कार्बन डाइऑक्साइड", "हाइड्रोजन"],
           answer: "हाइड्रोजन",
       },
       {
            question: "आभूषण बनाने के लिए कौन सी धातु का उपयोग होता है?",
          options: ["लोहा", "एल्युमीनियम", "सोना", "तांबा"],
            answer: "सोना",
       },
        {
             question: "सबसे भारी धातु कौन सी है?",
              options: ["सोना", "प्लेटिनम", "ऑस्मियम", "पारा"],
          answer: "ऑस्मियम",
       },
          {
             question: "किस धातु को चाकू से काटा जा सकता है?",
             options: ["सोना", "चाँदी", "सोडियम", "तांबा"],
          answer: "सोडियम",
        },
        {
             question: "धातुएं विद्युत और ऊष्मा की क्या होती हैं?",
            options: ["सुचालक", "कुचालक", "अर्धचालक", "अतिचालक"],
           answer: "सुचालक",
         },
        {
           question: "किस धातु का उपयोग विद्युत तारों में किया जाता है?",
           options: ["लोहा", "एल्यूमीनियम", "तांबा", "चाँदी"],
           answer: "तांबा",
       },
        {
           question: "कौन सी धातु कमरे के तापमान पर ठोस अवस्था में नहीं पाई जाती?",
          options: ["पारा", "एल्युमीनियम", "सोडियम", "चाँदी"],
          answer: "पारा",
        },
        {
         question: "धातुओं के ऑक्साइड किस प्रकार के होते हैं?",
           options: ["अम्लीय", "क्षारीय", "उदासीन", "उभयधर्मी"],
         answer: "क्षारीय",
        },
          {
          question: "कौन सा अधातु चमकदार होता है?",
           options: ["सल्फर", "फास्फोरस", "आयोडीन", "कार्बन"],
          answer: "आयोडीन",
        },
         {
          question: "pH स्केल में 7 से अधिक मान वाले विलयन क्या होते हैं?",
           options: ["अम्लीय", "उदासीन", "क्षारीय", "लवण"],
          answer: "क्षारीय",
         },
         {
           question: "उदासीन विलयन का pH मान कितना होता है?",
            options: ["0", "7", "14", "1"],
            answer: "7",
        },
          {
          question: "पेट में अम्लता को दूर करने के लिए किसका उपयोग किया जाता है?",
           options: ["अम्ल", "क्षार", "लवण", "पानी"],
           answer: "क्षार",
        },
        {
          question: "सिरका (vinegar) में कौन सा अम्ल मौजूद होता है?",
           options: ["हाइड्रोक्लोरिक अम्ल", "सल्फ्यूरिक अम्ल", "एसिटिक अम्ल", "नाइट्रिक अम्ल"],
           answer: "एसिटिक अम्ल",
         },
        ],
      },
     {
        section: "खंड 3: कार्बन एवं उसके यौगिक",
        questions: [
         {
           question: "कार्बन का वह गुण जिसके कारण यह विभिन्न तत्वों के साथ बंधन बना सकता है, कहलाता है?",
            options: ["कैटिनेशन", "आइसोमेरिज्म", "समानुकरण", "संयोजकता"],
            answer: "कैटिनेशन",
        },
           {
            question: "कार्बन के अपरूप कौन से हैं?",
             options: ["सोना और चाँदी", "हीरा और ग्रेफाइट", "लोहा और तांबा", "ऑक्सीजन और नाइट्रोजन"],
            answer: "हीरा और ग्रेफाइट",
        },
        {
          question: "किस हाइड्रोकार्बन में एक दोहरा बंधन होता है?",
           options: ["एल्केन", "एल्कीन", "एल्काइन", "एल्कोहल"],
          answer: "एल्कीन",
        },
         {
          question: "CH<sub>4</sub> किसका रासायनिक सूत्र है?",
            options: ["एथेन", "मीथेन", "प्रोपेन", "ब्यूटेन"],
          answer: "मीथेन",
        },
        {
          question: "एल्कोहल का क्रियात्मक समूह क्या है?",
            options: ["-COOH", "-CHO", "-OH", "-CO-"],
          answer: "-OH",
        },
        {
          question: "कीटोन का क्रियात्मक समूह क्या है?",
           options: ["-COOH", "-CHO", "-OH", "-CO-"],
          answer: "-CO-",
         },
         {
           question: "कार्बोक्सिलिक अम्ल का क्रियात्मक समूह क्या है?",
            options: ["-COOH", "-CHO", "-OH", "-CO-"],
            answer: "-COOH",
        },
         {
          question: "एल्डिहाइड का क्रियात्मक समूह क्या है?",
           options: ["-COOH", "-CHO", "-OH", "-CO-"],
           answer: "-CHO",
        },
        {
          question: "साबुन क्या है?",
           options: ["अम्ल", "क्षार", "लवण", "कार्बनिक यौगिक"],
           answer: "लवण",
       },
       {
           question: "पेट्रोलियम का मुख्य घटक क्या है?",
             options: ["एल्केन", "एल्कीन", "एल्काइन", "एल्कोहल"],
           answer: "एल्केन",
        },
        {
          question: "C<sub>6</sub>H<sub>12</sub>O<sub>6</sub> किसका रासायनिक सूत्र है?",
            options: ["चीनी", "ग्लूकोज", "अल्कोहल", "एसिटिक अम्ल"],
            answer: "ग्लूकोज",
       },
       {
            question: "सिरके में कौन सा अम्ल पाया जाता है?",
           options: ["सिट्रिक अम्ल", "लैक्टिक अम्ल", "एसिटिक अम्ल", "टार्टरिक अम्ल"],
           answer: "एसिटिक अम्ल",
        },
       {
            question: "कार्बनिक यौगिकों में कौन सा तत्व आवश्यक है?",
          options: ["ऑक्सीजन", "हाइड्रोजन", "नाइट्रोजन", "कार्बन"],
            answer: "कार्बन",
       },
      {
            question: "कौन सा हाइड्रोकार्बन सबसे सरल है?",
          options: ["एथेन", "मीथेन", "प्रोपेन", "ब्यूटेन"],
           answer: "मीथेन",
        },
        {
             question: "किस कार्बनिक यौगिक में एक त्रिबंध होता है?",
              options: ["एल्केन", "एल्कीन", "एल्काइन", "एल्कोहल"],
          answer: "एल्काइन",
       },
       {
             question: "एथेन का रासायनिक सूत्र क्या है?",
              options: ["CH<sub>4</sub>", "C<sub>2</sub>H<sub>6</sub>", "C<sub>3</sub>H<sub>8</sub>", "C<sub>4</sub>H<sub>10</sub>"],
            answer: "C<sub>2</sub>H<sub>6</sub>",
        },
         {
           question: "अल्कोहल के नाम में प्रत्यय क्या होता है?",
           options: ["ओल", "ईन", "आइन", "अल"],
         answer: "ओल",
        },
         {
           question: "एल्डिहाइड के नाम में प्रत्यय क्या होता है?",
          options: ["ओल", "ईन", "आइन", "अल"],
           answer: "अल",
       },
          {
          question: "किस कार्बनिक यौगिक में -COOH समूह होता है?",
           options: ["एल्कोहल", "एल्डिहाइड", "कीटोन", "कार्बोक्सिलिक अम्ल"],
          answer: "कार्बोक्सिलिक अम्ल",
        },
         {
            question: "एल्केन किस प्रकार के बंधन से जुड़े होते हैं?",
           options: ["एकल बंधन", "दोहरा बंधन", "तिहरा बंधन", "कोई बंधन नहीं"],
            answer: "एकल बंधन",
        },
          {
            question: "दही में कौन सा अम्ल होता है?",
             options: ["सिट्रिक अम्ल", "लैक्टिक अम्ल", "टार्टरिक अम्ल", "एसिटिक अम्ल"],
           answer: "लैक्टिक अम्ल",
        },
         {
            question: "टमाटर में कौन सा अम्ल पाया जाता है?",
            options: ["सिट्रिक अम्ल", "लैक्टिक अम्ल", "ऑक्सालिक अम्ल", "एसिटिक अम्ल"],
            answer: "ऑक्सालिक अम्ल",
       },
           {
            question: "बेकिंग सोडा का रासायनिक नाम क्या है?",
           options: ["सोडियम क्लोराइड", "सोडियम कार्बोनेट", "सोडियम बाइकार्बोनेट", "कैल्शियम क्लोराइड"],
           answer: "सोडियम बाइकार्बोनेट",
        },
       {
           question: "धावन सोडा का रासायनिक सूत्र क्या है?",
           options: ["NaCl", "NaHCO<sub>3</sub>", "Na<sub>2</sub>CO<sub>3</sub>.10H<sub>2</sub>O", "CaCl<sub>2</sub>"],
           answer: "Na<sub>2</sub>CO<sub>3</sub>.10H<sub>2</sub>O",
        },
          {
             question: "प्लास्टर ऑफ पेरिस का रासायनिक सूत्र क्या है?",
          options: ["CaSO<sub>4</sub>", "CaSO<sub>4</sub>.2H<sub>2</sub>O", "CaSO<sub>4</sub>.1/2H<sub>2</sub>O", "CaCO<sub>3</sub>"],
            answer: "CaSO<sub>4</sub>.1/2H<sub>2</sub>O",
       },
      ],
    },
      {
        section: "खंड 4: तत्वों का आवर्त वर्गीकरण",
        questions: [
        {
          question: "आधुनिक आवर्त सारणी किस नियम पर आधारित है?",
          options: ["परमाणु द्रव्यमान", "परमाणु संख्या", "तत्वों की प्रकृति", "तत्वों का आयतन"],
          answer: "परमाणु संख्या",
        },
          {
            question: "आवर्त सारणी के समूह में ऊपर से नीचे जाने पर परमाणु आकार पर क्या प्रभाव पड़ता है?",
           options: ["बढ़ता है", "घटता है", "कोई प्रभाव नहीं पड़ता", "अनियमित परिवर्तन"],
            answer: "बढ़ता है",
        },
        {
          question: "आवर्त सारणी के आवर्त में बाएं से दाएं जाने पर परमाणु आकार पर क्या प्रभाव पड़ता है?",
           options: ["बढ़ता है", "घटता है", "कोई प्रभाव नहीं पड़ता", "अनियमित परिवर्तन"],
          answer: "घटता है",
        },
         {
          question: "आवर्त सारणी के किस समूह में अक्रिय गैसें रखी गई हैं?",
            options: ["समूह 1", "समूह 2", "समूह 17", "समूह 18"],
          answer: "समूह 18",
        },
        {
          question: "आवर्त सारणी के किस समूह में हैलोजन तत्व रखे गए हैं?",
            options: ["समूह 1", "समूह 2", "समूह 17", "समूह 18"],
          answer: "समूह 17",
        },
         {
          question: "सबसे विद्युत ऋणात्मक तत्व कौन सा है?",
           options: ["फ्लोरीन", "क्लोरीन", "ऑक्सीजन", "नाइट्रोजन"],
           answer: "फ्लोरीन",
        },
        {
          question: "सबसे अधिक विद्युत धनात्मक तत्व कौन सा है?",
           options: ["सोडियम", "पोटैशियम", "सीजियम", "लिथियम"],
           answer: "सीजियम",
       },
       {
           question: "मेंडेलीव की आवर्त सारणी किस पर आधारित थी?",
             options: ["परमाणु संख्या", "परमाणु द्रव्यमान", "तत्वों की प्रकृति", "तत्वों का आयतन"],
           answer: "परमाणु द्रव्यमान",
        },
        {
          question: "आधुनिक आवर्त सारणी में कितने आवर्त होते हैं?",
            options: ["6", "7", "8", "9"],
            answer: "7",
       },
      {
            question: "आधुनिक आवर्त सारणी में कितने समूह होते हैं?",
           options: ["16", "17", "18", "19"],
           answer: "18",
        },
       {
           question: "धातुएं आवर्त सारणी के किस भाग में स्थित होती हैं?",
           options: ["बाएँ ओर", "दाएँ ओर", "मध्य में", "कहीं भी"],
           answer: "बाएँ ओर",
        },
        {
          question: "अधातुएं आवर्त सारणी के किस भाग में स्थित होती हैं?",
            options: ["बाएँ ओर", "दाएँ ओर", "मध्य में", "कहीं भी"],
            answer: "दाएँ ओर",
        },
          {
          question: "उपधातुएं आवर्त सारणी के किस भाग में स्थित होती हैं?",
           options: ["बाएँ ओर", "दाएँ ओर", "मध्य में", "कहीं भी"],
            answer: "मध्य में",
       },
        {
            question: "आवर्त सारणी में तत्वों को किस क्रम में व्यवस्थित किया गया है?",
              options: ["परमाणु द्रव्यमान का बढ़ता क्रम", "परमाणु संख्या का बढ़ता क्रम", "तत्वों की प्रकृति का क्रम", "तत्वों के आयतन का क्रम"],
          answer: "परमाणु संख्या का बढ़ता क्रम",
        },
          {
           question: "परमाणु संख्या की खोज किसने की थी?",
            options: ["मेंडेलीव", "हेनरी मोसले", "डोबरेनर", "न्यूलैंड्स"],
            answer: "हेनरी मोसले",
        },
         {
             question: "डोबरेनर ने किस नियम का प्रतिपादन किया था?",
             options: ["त्रिक नियम", "अष्टक नियम", "आधुनिक नियम", "आवर्त नियम"],
          answer: "त्रिक नियम",
        },
         {
             question: "न्यूलैंड्स ने किस नियम का प्रतिपादन किया था?",
            options: ["त्रिक नियम", "अष्टक नियम", "आधुनिक नियम", "आवर्त नियम"],
           answer: "अष्टक नियम",
         },
        {
           question: "सबसे कम प्रतिक्रियाशील तत्व किस समूह में पाए जाते हैं?",
           options: ["समूह 1", "समूह 2", "समूह 17", "समूह 18"],
           answer: "समूह 18",
        },
           {
          question: "तत्वों के गुणों को कौन निर्धारित करता है?",
           options: ["परमाणु द्रव्यमान", "परमाणु संख्या", "परमाणु का आकार", "परमाणु का आयतन"],
           answer: "परमाणु संख्या",
        },
          {
           question: "विद्युत ऋणात्मकता आवर्त सारणी में बाएं से दाएं जाने पर क्या होती है?",
            options: ["बढ़ती है", "घटती है", "कोई परिवर्तन नहीं होता", "अनियमित परिवर्तन"],
           answer: "बढ़ती है",
        },
        {
          question: "सोडियम क्लोराइड (नमक) किस प्रकार का यौगिक है?",
           options: ["अम्ल", "क्षार", "लवण", "उदासीन"],
         answer: "लवण",
        },
          {
           question: "दाँतों के क्षय को रोकने के लिए कौन सा टूथपेस्ट इस्तेमाल करना चाहिए?",
            options: ["अम्लीय टूथपेस्ट", "क्षारीय टूथपेस्ट", "उदासीन टूथपेस्ट", "सादा पानी"],
           answer: "क्षारीय टूथपेस्ट",
       },
        {
             question: "पीएच पेपर किस रंग का होता है जब एक क्षारीय विलयन में डुबोया जाता है?",
            options: ["लाल", "नीला", "हरा", "पीला"],
           answer: "नीला",
        },
      ],
    },
    ];
         const quizContainer = document.getElementById('quiz-container');
        const sectionSelector = document.getElementById('section-selector');
        let currentSection = null;
        let totalScore = 0;


         quizData.forEach((sectionData, sectionIndex) => {
            const sectionDiv = document.createElement('div');
            sectionDiv.classList.add('section');
             if (sectionIndex === 0) {
                sectionDiv.classList.add('active');
                currentSection = sectionDiv;

            }
            sectionDiv.innerHTML = `<h2>${sectionData.section}</h2>`;
            const form = document.createElement('form');
             form.id = `section-form-${sectionIndex}`;

             let questionCounter = 0;
              sectionData.questions.forEach((q, questionIndex) => {
                const questionDiv = document.createElement('div');
                questionDiv.classList.add('question');
                questionDiv.innerHTML = `<p>${++questionCounter}. ${q.question}</p>`;

                const answerOptionsDiv = document.createElement('div');
                answerOptionsDiv.classList.add('answer-options');
                q.options.forEach((option, index) => {
                    const label = document.createElement('label');
                    const input = document.createElement('input');
                    input.type = 'radio';
                    input.name = `q${questionCounter}`;
                    input.value = option;
                    label.appendChild(input);
                    label.appendChild(document.createTextNode(option));
                    answerOptionsDiv.appendChild(label);
                });
                questionDiv.appendChild(answerOptionsDiv);
                form.appendChild(questionDiv);
            });
               const submitButton = document.createElement('button');
             submitButton.type = 'submit';
             submitButton.textContent = 'जमा करें';
            form.appendChild(submitButton);
              sectionDiv.appendChild(form);

             quizContainer.appendChild(sectionDiv);

               form.addEventListener('submit', function(event) {
                 event.preventDefault();
                  let sectionScore = 0;
                  const feedbackDiv = document.getElementById('feedback');
                  let sectionQuestion = 0;
                   sectionData.questions.forEach(q =>{
                       sectionQuestion++;
                         const selectedAnswer = document.querySelector(`input[name="q${sectionQuestion}"]:checked`);
                     if(selectedAnswer){
                         if(selectedAnswer.value === q.answer){
                             sectionScore++;
                            feedbackDiv.innerHTML += `<p class="correct">खंड ${sectionIndex + 1} प्रश्न ${sectionQuestion}: सही जवाब</p>`;
                         } else{
                              feedbackDiv.innerHTML += `<p class="incorrect">खंड ${sectionIndex + 1} प्रश्न ${sectionQuestion}: गलत जवाब</p>`;
                         }
                     } else{
                         feedbackDiv.innerHTML += `<p class="incorrect">खंड ${sectionIndex + 1} प्रश्न ${sectionQuestion}: जवाब नहीं दिया</p>`;
                     }

                   });
                 totalScore += sectionScore;
                 document.getElementById('score').textContent = totalScore;
                document.getElementById('results').style.display = 'block';
                form.reset();
            });
        });


       sectionSelector.addEventListener('change', function(event) {
        const selectedSectionIndex = parseInt(event.target.value);

          if(currentSection){
              currentSection.classList.remove('active')
          }
           const selectedSectionDiv = quizContainer.children[selectedSectionIndex];
           selectedSectionDiv.classList.add('active')
           currentSection = selectedSectionDiv;


        });
    </script>

</body>
</html>
