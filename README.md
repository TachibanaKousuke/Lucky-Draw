# README

This web-app is a random pick-up website intended for students in Class 17, Grade 2024 of Mianyang Dongchen Middle School, which includes a funny "lucky draw" which calls individuals by their nickname, showing their avatar with a hovering animation, and have an alternative to see their real names. Users are required to customize the database before using. Follow the instructions to set up.

## START UP

Clone this repository to your local, including intex.html, database-generator.py (optional) and nicknames.xlsx (optional).

## STATISTICS COLLECTING

To start with, you need to open up a new .xlsx form which contains all your statistics. The form should have several columns, each named "网名""真实姓名""头像位置""分科" in their first row. The order of the columns is not limited. The form should look like this:
![](https://pic1.imgdb.cn/item/693e2ab425ec9c13612c6c20.png)

## DATABASE GENERATING

After collecting and analyzing your statistics, you'll need to convert your statistics into a utilizable database which the web can read. The database consists of four parts: students, skills, teachers and start phrases.

The formation of the student database should be like this:

```html
const database = [
            { nickname: "A", realname: "AA", avatarUrl: "https://AAA.jpg", subject: "政治" },
            { nickname: "B", realname: "BB", avatarUrl: "https://BBB.jpg", subject: "生物" },
            { nickname: "C", realname: "CC", avatarUrl: "https://CCC.jpg", subject: "政治" },
            { nickname: "D", realname: "DD", avatarUrl: "https://DDD.jpg", subject: "生物" },

        ];
```

You can customize nickname, real name, avatar URL and subject up to your need.

But if your form is too big to type in one by one, here's a short cut for you. Just clone the database-generator.py in this repository, and put the .py file and your .xlsx file in the same folder. Then replace the example .xlsx name in line 95 by your file name.

![](https://pic1.imgdb.cn/item/693e2faffe7cfeca38251c82.png)

Then open Terminal or PowerShell.

```python
pip install pandas openpyxl
```

Then type in:

```python
python database-generator.py
```

You would get a .txt file in the same folder where the .py file lies, named database_output.txt. With just a simple copy and paste, you can finish the setup of student database.

![](https://pic1.imgdb.cn/item/693e312025ec9c13612ca7c2.png)

The formation of the skill database should be like this:

```
        const SKILLS = [
            { type: "skill", nickname: "万箭齐发", realname: "万箭齐发", avatarUrl: "", isSpecial: true, rarity: 'legend', className: 'skill-item' },
            { type: "skill", nickname: "铁索连环", realname: "铁索连环", avatarUrl: "", isSpecial: true, rarity: 'epic', className: 'skill-item' },
        ];
```

You can customize nickname, real name( the two should be the same) ,and rarity( choose from "epic""legend""rare").

The formation of the teacher database should be like this:

```html
        const TEACHERS = [
            { type: "teacher", nickname: "E", realname: "EE", avatarUrl: "", isSpecial: true, rarity: 'legend', className: 'teacher-item' },
            { type: "teacher", nickname: "F", realname: "FF", avatarUrl: "", isSpecial: true, rarity: 'epic', className: 'teacher-item' },
        ];
```

The rule is the same as the skills.

The formation of the start phrases should be like this:

```
        const startPhrases = [
            "让我看看谁在紧张", "是谁的小鹿在乱撞", "深呼吸，头晕是正常的",
            "别躲了，我都看到你了", "此时一名幸运观众汗流浃背", "命运的齿轮开始转动",
            "只是抽个查，别慌", "眼神别飘，看着我", "准备好你的表演了吗", "让我康康是谁这么幸运"
        ];
```

You can add your own interesting statistics.

Then fill your own statistics respectively into intex.html.

## DEPLOYMENT

You can host it on GitHub Pages in 3 minutes (zero-config, no build step)

First,you create a new repo and upload the files(intex.html must, others optional).

Then turn on GitHub Pages, choose deploy from a branch → choose main (or master) → / (root) → Save.

GitHub will give you a live URL in 5-30 s, e.g.
`https://YOUR_USERNAME.github.io/REPO_NAME/`
Copy it—that’s your public site.

## Done! Share the URL with the class.