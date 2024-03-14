# shiny-eureka
function countdownToTime(targetTime) {
    // Get the current date and time
    var now = new Date();

    // Get the target time
    var target = new Date();
    target.setHours(15);    // 3 PM
    target.setMinutes(10);  // 10 minutes
    target.setSeconds(30);  // 30 seconds

    // If the target time has already passed for today, set it for tomorrow
    if (now > target) {
        target.setDate(target.getDate() + 1);
    }

    // Calculate the time difference between now and the target time
    var timeDiff = target - now;

    // Calculate hours, minutes, and seconds
    var hours = Math.floor(timeDiff / (1000 * 60 * 60));
    var minutes = Math.floor((timeDiff % (1000 * 60 * 60)) / (1000 * 60));
    var seconds = Math.floor((timeDiff % (1000 * 60)) / 1000);

    // Display the countdown
    console.log("Countdown to 3:10:30 PM:", hours + "h " + minutes + "m " + seconds + "s");
}

// Call the function to start the countdown
countdownToTime();
