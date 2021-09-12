- 👋 Hi, I’m @kariskaka
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
kariskaka/kariskaka is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// paste this to the developer console
SCORE = 13379;
data = {
  "score":714,
  "url":"/game/karatekid2",
  "play_time":52,
  "hash":"{\"ct\":\"WFND2Rlq7gvKoMBxMhOOTScSvgsQVxr5CWwoKq9oMaWXu5kHJuYoGqIkFWb8NZ1MT8FebP1RHW7dLZ66YbCYKA39YPLtvkONxszWpN0aeAY=\",\"iv\":\"81fc80601f7c64317c3029fa4edd18d4\",\"s\":\"7501f4ecbe09df31\"}",
  "username":null,
  "anonymous_id":null,
  "game_state_data":"{\"totalBlockCnt\":$$$}"
};

hash = CryptoJS.AES.encrypt(
  JSON.stringify({
    score: SCORE, timestamp: new Date().getTime()
  }),
  "crmjbjm3lczhlgnek9uaxz2l9svlfjw14npauhen", // $(#dataId).attr('data-id');
  {
    format: CryptoJSAesJson
  }
).toString();
data.score = SCORE;
data.url = window.location.pathname;
data.hash = hash;
data.game_state_data = data.game_state_data.replace("$$$", parseInt(2628).toString());//parseInt(2628/646 * SCORE).toString());
data.play_time = 16;//parseInt((714 / 52) * SCORE);
gameeUI.sendScoreData(data);
data.hash = CryptoJS.AES.encrypt(
  JSON.stringify({
    score: SCORE, timestamp: new Date().getTime()
  }),
  "crmjbjm3lczhlgnek9uaxz2l9svlfjw14npauhen", // $(#dataId).attr('data-id');
  {
    format: CryptoJSAesJson
  }
).toString();
gameeUI.sendScoreData(data);
