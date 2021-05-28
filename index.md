<!DOCTYPE html>
<html lang="en">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta name="theme-color" content="#000000" />
    <meta name="description" content="">

    <link rel="shortcut icon" type="image/png" />

    <link rel="preconnect" href="https://api.github.com" crossorigin>

    <link rel="preload" as="style" href="https://fonts.googleapis.com/css?family=Questrial&display=swap">
    <link rel="preload" as="image"
        href="https://images.unsplash.com/photo-1498590880827-3f79fdcd7fbe?q=0&fm=webp&cs=tinysrgb&w=1080">
    <link rel="preload" as="font" href="fa.woff">

    <style>@import url(https://fonts.googleapis.com/css?family=Questrial&display=swap);@font-face{font-family:fa;src:url(fa.woff) format('woff');font-weight:400;font-style:normal;font-display:block}[class^=fa-]{font-family:fa!important;font-style:normal;font-weight:400;font-variant:normal;text-transform:none;line-height:1;-webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale}.fa-star:before{content:"\f005"}.fa-map-marker:before{content:"\f041"}.fa-group:before{content:"\f0c0"}.fa-users:before{content:"\f0c0"}.fa-chain:before{content:"\f0c1"}.fa-link:before{content:"\f0c1"}.fa-envelope:before{content:"\f0e0"}.fa-code:before{content:"\f121"}.fa-code-branch:before{content:"\f126"}.fa-user-tie:before{content:"\f27e"}body{margin:0;padding:0;width:100vw;background:var(--bg-color);color:var(--text-color);max-width:100vw;overflow-x:hidden;align-items:center;font-family:Questrial,sans-serif;line-height:1.2}#profile{width:24vw;padding:4vh 3vw;height:92vh;display:flex;flex-direction:column;justify-content:center;text-align:left;background:var(--background-image) center center;background-size:cover!important;background-repeat:no-repeat;position:fixed;color:#fff!important}#display{width:64vw;padding:4vh 3vw;height:92vh;display:inline-block;padding-left:33vw}#display h1{font-size:50px;color:var(--text-color);font-weight:700;font-family:Questrial,sans-serif}#footer{width:100%;padding:8vh 0;text-align:center}#footer a{color:var(--text-color)!important;text-decoration:none;font-family:Questrial,sans-serif;font-weight:700}#profile_img{width:180px;height:180px;border-radius:5px;background-size:cover!important}#profile div{font-weight:700;margin:1.5vh 0}#username{font-size:18px;font-weight:700}#username span{font-size:24px}#userbio{font-size:26px;font-family:Questrial,sans-serif;width:100%}#about{font-size:18px;font-family:Questrial,sans-serif}#about span{margin:1vh 0;display:block}#about span i{font-size:16px}#work{margin:2vh 0;padding:4vh 0!important}#forks{margin:2vh 0;padding:4vh 0!important}.projects{columns:2}.projects section{width:85%;padding:2.5vh 5%;display:inline-block;border-radius:5px;color:var(--text-color);border:1px solid rgb(0,0,0,.08);box-shadow:0 0 0 rgb(0,0,0,0);transition:.4s ease-in-out;margin:2vh 0;transform:scale(1)}.projects section:hover{cursor:pointer;border:1px solid rgb(0,0,0,0);box-shadow:0 15px 35px rgb(0,0,0,.06);transform:scale(1.03)}.section_title{font-size:24px;font-weight:700;margin:1vh 0;word-wrap:break-word}.about_section{font-size:18px;font-family:Questrial,sans-serif;margin:2vh 0;font-weight:700;word-wrap:break-word}.bottom_section{margin:1vh 0;font-size:14px;word-wrap:break-word}.bottom_section span{margin-right:20px;font-weight:700}.bottom_section span i{font-size:16px}::selection{color:var(--bg-color);background:var(--text-color)}@media (max-width:800px){#profile{width:90vw;padding:4vh 5vw;height:60vh;text-align:center;position:relative}#display{width:90vw;padding:4vh 5vw;height:auto;display:inline-block;padding-left:5vw}#profile_img{width:120px;height:120px;margin:0 auto!important}#work{margin:0}.projects{columns:1}.projects section{width:88%}}::-webkit-scrollbar{width:5px;height:5px}::-webkit-scrollbar-track{background:var(--bg-color)}::-webkit-scrollbar-thumb{background:var(--text-color)}:root{--bg-color:rgb(10,10,10);--text-color:#fff;--blog-gray-color:rgb(180,180,180);--background-image:linear-gradient(90deg,rgba(10,10,10,.6),rgb(10,10,10,1)),url(https://images.unsplash.com/photo-1498590880827-3f79fdcd7fbe?q=0&fm=webp&cs=tinysrgb&w=1080);--background-background:linear-gradient(0deg,rgba(10,10,10,1),rgba(10,10,10,.6)),url("") center center fixed;--height:50vh}#display h1{-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:#fff}.projects section{background:#141414}@media (max-width:800px){:root{--background-image:linear-gradient(0deg,rgba(10,10,10,1),rgb(10,10,10,0)),url("")!important}}</style>
</head>

<body>

    <div id="profile">
        <div id="profile_img"></div>
        <div id="username"></div>
        <div id="userbio"></div>
        <div id="about"></div>
    </div>
    <div id="display">
        <div id="work">
            <h1>Work.</h1>
            <div class="projects" id="work_section"></div>
        </div>
        <div id="forks" style="display: block;">
            <h1>Forks.</h1>
            <div class="projects" id="forks_section"></div>
        </div>
        <div id="footer">
            <a href="https://github.com/imfunniee" target="_blank" rel="noopener">made on earth by a human</a>
        </div>
    </div>

    <script>
        // Returns HTML string of these repo boxes to append to DOM. To learn about attributes of repo see https://developer.github.com/v3/search/#example
        function renderRepo(repo) {
            return `
                <a href="${repo.html_url}" target="_blank" rel="noopener">
                    <section>
                        <div class="section_title">${repo.name}</div>
                        <div class="about_section">
                            <span style="display:block;">${repo.description}</span>
                        </div>
                        <div class="bottom_section">
                            <span style="display:inline-block;"><i class="fa-code"></i> ${repo.language}</span>
                            <span><i class="fa-star"></i> ${repo.stargazers_count}</span>
                            <span><i class="fa-code-branch"></i> ${repo.forks}</span>
                        </div>
                    </section>
                </a>`
        }

        // Because Github sets subdomain to your username we can extract your Github username from subdomain.
        var username = window.location.host.split('.')[0];
        document.title = username;

        // Fetches data about user itself to render left side of page.
        fetch(`https://api.github.com/users/${username}`).then(response => response.json()).then(user => {
            document.title = user.name;
            document.querySelector("meta[name='description']").setAttribute("content", user.bio);
            document.querySelector("link[rel='shortcut icon']").setAttribute("href", user.avatar_url);
            document.getElementById('profile_img').style = `background: url(${user.avatar_url}) center;`;
            document.getElementById('username').innerHTML = `<span style="display:block;">${user.name}</span>@${user.login}`;
            document.getElementById('userbio').innerHTML = user.bio;
            document.getElementById('about').innerHTML += user.company ? `<span style="display:block;"><i class="fa-users"></i> ${user.company}</span>` : "";
            document.getElementById('about').innerHTML += user.email ? `<span style="display:block;"><i class="fa-envelope"></i> ${user.email}</span>` : "";
            document.getElementById('about').innerHTML += user.blog ? `<span style="display:block;"><i class="fa-link"></i> ${user.blog}</span>` : "";
            document.getElementById('about').innerHTML += user.location ? `<span style="display:block;"><i class="fa-map-marker"></i> ${user.location}</span>` : "";
            document.getElementById('about').innerHTML += user.hireable ? `<span style="display:block;"><i class="fa-user-tie"></i> Available for hire</span>` : "";
        });

        // Fetches only non-fork repositories sorted by star count.
        fetch(`https://api.github.com/search/repositories?q=user:${username} fork:false&sort=stars`).then(response => response.json()).then(repositories => {
            repositoriesDom = document.getElementById('work_section');
            if (!repositories.total_count)
                repositoriesDom.parentElement.parentElement.removeChild(repositoriesDom.parentElement);
            repositories.items.forEach(repo => {
                repositoriesDom.innerHTML += renderRepo(repo);
            });
        });

        // Fetches only fork repositories sorted by star count.
        fetch(`https://api.github.com/search/repositories?q=user:${username} fork:only&sort=stars`).then(response => response.json()).then(forks => {
            forksDom = document.getElementById('forks_section');
            if (!forks.total_count)
                forksDom.parentElement.parentElement.removeChild(forksDom.parentElement);
            forks.items.forEach(fork => {
                forksDom.innerHTML += renderRepo(fork);
            });
        });
    </script>
</body>

</html>
