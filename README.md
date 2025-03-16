# Hi there! 👋 I'm Shaswat Subudhi  

- 🚀 Passionate about coding, problem-solving, and building awesome projects.
- 📖 I'm enrolled in Siksha 'O' Anusandhan University to pursue a B-Tech in Computer Science Engineering.
- 🌱 Currently, I'm learning Python & AiMl.

💡 **"Turning coffee into code, one bug at a time."**  

<img align="center" src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f1b00d6c9.gif" height="300" />

## 🔧 Technologies & Skills

- 💻 **Languages:**

  <div align="center">
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/java.png" alt="Java" title="Java"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/html.png" alt="HTML" title="HTML"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/css.png" alt="CSS" title="CSS"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/bootstrap.png" alt="Bootstrap" title="Bootstrap"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/python.png" alt="Python" title="Python"/></code>
</div>

- 🔧 **Tools:**

  <div align="center">
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/intellij.png" alt="IntelliJ" title="IntelliJ"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/git.png" alt="Git" title="Git"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/pycharm.png" alt="PyCharm" title="PyCharm"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/eclipse.png" alt="eclipse" title="eclipse"/></code>
	<code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/visual_studio_code.png" alt="Visual Studio Code" title="Visual Studio Code"/></code>
</div>  

## 📈 GitHub Stats  
![Shaswat's GitHub Stats](https://github-readme-stats.vercel.app/api?username=ShaswatSubudhi&show_icons=true&theme=dark)
[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com?user=ShaswatSubudhi&theme=transparent&hide_border=true&border_radius=5&short_numbers=true&sideLabels=EB5454)](https://git.io/streak-stats)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=ShaswatSubudhi&layout=compact&theme=dark)

## 👀 Profile Views 👀

![](https://komarev.com/ghpvc/?username=ShaswatSubudhi)

## 🌍 Connect with Me  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](#)  
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/shaswat_subudhi/) 

## I'm a gamer too so you may find me here too...
<a href="f253c0bd90a74586a47f57f366cfc233" target="blank"><img align="center" src="https://upload.wikimedia.org/wikipedia/commons/3/31/Epic_Games_logo.svg" height="100" /></a>
<a href="https://steamcommunity.com/id/ShaswatSubudhi25/" target="blank"><img align="center" src="https://upload.wikimedia.org/wikipedia/commons/8/83/Steam_icon_logo.svg" height="100" /></a>
---

✨ Always learning, always coding. Let's build something amazing! 🚀  



name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
 steps:
      - name: generate github-contribution-grid-snake.svg
        uses: ShaswatSubudhi/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
	name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} 
