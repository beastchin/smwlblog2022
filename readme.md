
            var hour = now.getHours();      // 得到小时
            var minu = now.getMinutes();    // 得到分钟
            var sec = now.getSeconds();     // 得到秒钟

            if (hour > 0 && hour <= 2) text = "丑时";
            else if (hour > 2 && hour <= 4) text = "寅时";
            else if (hour > 4 && hour <= 6) text = "卯时";
            else if (hour > 6 && hour <= 8) text = "辰时";
            else if (hour > 8 && hour <= 10) text = "巳时";
            else if (hour > 10 && hour <= 12) text = "午时";
            else if (hour > 12 && hour <= 14) text = "未时";
            else if (hour > 14 && hour <= 16) text = "申时";
            else if (hour > 16 && hour <= 18) text = "酉时";
            else if (hour > 18 && hour <= 20) text = "戌时";
            else if (hour > 20 && hour <= 22) text = "亥时";
            else text = "子时";
            $('#time_show').html('<a href="https://www.beijing-time.org/shichen" target="_blank">' + text + '</a>');

            intDiff++;
        }, 1000);
    }
    var nowtime = timestamp(); // 现行时间戳
  
