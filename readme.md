<script>
    var start = new Date().getTime();
    function timestamp() {
        let outcome = Math.round(new Date().getTime() / 1000).toString();
        return outcome
    }
    function timer(intDiff) {
        myTimer = window.setInterval(function () {
            var day = 0,
                hour = 0,
                minute = 0,
                second = 0;//时间默认值
            if (intDiff > 0) {
                day = Math.floor(intDiff / (60 * 60 * 24));
                hour = Math.floor(intDiff / (60 * 60)) - (day * 24);
                minute = Math.floor(intDiff / 60) - (day * 24 * 60) - (hour * 60);
                second = Math.floor(intDiff) - (day * 24 * 60 * 60) - (hour * 60 * 60) - (minute * 60);
            }
            if (hour <= 9) hour = "0" + hour;
            if (minute <= 9) minute = "0" + minute;
            if (second <= 9) second = "0" + second;

            $('#day_show').html(day + '天 ' + hour + '时 ' + minute + '分 ' + second + '秒');

            var now = new Date();
            var year = now.getFullYear();   // 得到年份
            var month = now.getMonth();     // 得到月份
            var date = now.getDate();       // 得到日期
            var day = now.getDay();         // 得到周几
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
    var mytime = 1663686269; // 设置安装时间（安装日期时间戳）
    timer(nowtime - mytime); // 启动循环

    // 页面加载完成后执行
    $(document).ready(function () {
        // $('.footer-new').hide(); // 隐藏底部
        $('.footer-new').show(); // 显示底部
        $('#load_show').html((new Date().getTime() - start) + 'ms');
    });
</script>
