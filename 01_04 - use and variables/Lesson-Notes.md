# import and use and advanced architecture

دبا فاش كدير شي ملف جديد ديال sass خاص تكون عارف واش باغي الملف لغرض الاستدعاء من بعد اولا بغيتي اي حاجة ديرها فيه ادار ليها compile directly لملف css

باش تخلي ال compiler يتجاهل ملف sass ويخليه لغرض ال import only خاصك ضيف فاللول ديال السمة ديال ملف ال sass "_" يعني مثلا `global-rules.scss_`



# Variables

اولا: ال syntax ديال المتغريات فال sass هو هدا

    $main_color: #eee;

ثانيا: فاش كدير ملف خاص بال variables و كتستدعيه فال main.scss فراه مغيقدش اقرا داكشي لي فيه

مثلا

    @use "./sass/layout/variables"

خاص ضروي دير هاد ال syntax 

    @use "./sass/layout/variables" as *

اولا تقد تستدعيه عادي ولكن فلوقت لي غدير شي متغير من داك الملف دير هاد ال syntax



    .someThing {
        background-color: variables.$maiOne;
    }


ثالثا: وهي انك تقدر تبدل قيمة المتغير 


    $main_color: red;
    
    .header {
        color: blue !global;
    }


هنايا القيمة ديال main_color غتبدل



وتقد حتا تستعمل المتغير مع ال media queries

    $small_devices: "max-width: 570px";
    
    @media($small_devices) {
        somthing here
    }

    // in css file

    
    @media (max-width: 570px) {
        .container {
            width: 200px;
        }
    }

<br>

# Nesting and Parent Element

دبا هدا هو ال nesting العادي فال sass

    .parent {
        color: blue;

        .childe {
            font-size: 20px;

            .grandChilde {
                font-weight: 400;
            }
        }
    }

    // Css

    .parent {
        color: blue;
    }
    .parent .childe {
        font-size: 20px;
    }
    .parent .childe .grandChilde {
        font-weight: 400;
    }
