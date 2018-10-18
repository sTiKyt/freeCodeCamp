# Локальная установка freeCodeCamp

Следуйте этим рекомендациям для локальной установки freeCodeCamp. Это очень рекомендуется если вы собираетесь вкладываться регулярно.

Некоторые процессы вроде предпросмотра страниц для руководства, кодерских испытаний, отладки и исправления ошибок в базе кода, требуют от вас локальной установки freeCodeCamp.

## Копирование репозитория на GitHub

['Копирование'](https://help.github.com/articles/about-forks/) это шаг на котором вы получаете вашу собственную копию основного репозитория freeCodeCamp (также _repo_) на GitHub.

Это важно, потому что этот способ позволит вам работать с собственной копией freeCodeCamp на GitHub, или загрузить её для работы локально. Позже, вы сможете запросить добавление изменений в основной репозиторий при помощи запроса на добавление (pull request'a).

> **Профессиональный совет:**
> Репозиторий по адресу `https://github.com/freeCodeCamp/freeCodeCamp` в основном называется `главным` репозиторием.
> Ваша копия по адресу `https://github.com/ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ/freeCodeCamp` в основном называется `источником` для другого репозитория.

**Следуйте этим шагам чтобы скопировать `https://github.com/freeCodeCamp/freeCodeCamp` репозиторий:**

1. Перейдите на GitHub репозиторий freeCodeCamp: <https://github.com/freeCodeCamp/freeCodeCamp>
2. нажмите кнопку "Fork" в правом верхнем углу интерфейса ([Больше подробностей тут](https://help.github.com/articles/fork-a-repo/))
3. После копирования репозитория, вы будете перемещены к вашей собственной копии freeCodeCamp `https://github.com/ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ/freeCodeCamp`

![GIF - Как скопировать freeCodeCamp на Github](/docs/images/github/how-to-fork-freeCodeCamp.gif)

## Подготовка среды разработки

После начальных настроек вам необходимо подготовить среду разработки. Это характерно для многих рабочих процессов разработки, и вам понадобится сделать это только один раз.

**Следуйте этим шагам чтобы подготовить вашу рабочую среду:**

1. Установите [Git](https://git-scm.com/) или ваш любимый Git клиент, если вы не сделали этого раньше. Обновитесь до последней версии, если ваш клиент предустановлен с вашей ОС, то он мог устареть.

2. (Необязательно, но рекомендуется) [Установить SSH ключ](https://help.github.com/articles/generating-an-ssh-key/) для GitHub.

3. Установите редактор кода на свой выбор.

    Мы очень рекомендуем использовать [VS Code](https://code.visualstudio.com/) или [Atom](https://atom.io/). Это отличные бесплатные редакторы кода с открытым исходным кодом.

4. Установите статический анализатор (также lint) для вашего редактора кода.

    У вас в редакторе должен быть запущен [ESLint](http://eslint.org/docs/user-guide/integrations.html), и он подсветит все что не соответствует с [руководством JavaScript стиля от freeCodeCamp](http://forum.freecodecamp.org/t/free-code-camp-javascript-style-guide/19121).

    > Пожалуйста не игнорируйте любые ошибки статического анализатора. Они предназначены чтобы **помочь** вам, для обеспечения чистого и простого кода.

## Клонирование вашей копии freeCodeCamp

['Клонирование'](https://help.github.com/articles/cloning-a-repository/) это шаг в котором вы **скачиваете** копию репозитория, пренадлежащую вам или кому-либо еще, из `удаленной` локации. В вашем случае, эта удаленная локация ваша `копия` репозитория freeCodeCamp, она должна быть доступна по адресу `https://github.com/ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ/freeCodeCamp`.

Выполните эти команды на вашем устройстве:

1. Откройте Терминал / Командную строку / Оболочку терминала в директории вашего проекта

    _т.е.: `/директориявашегопроекта/`_

2. Клонируйте вашу копию freeCodeCamp, заменив `ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ` вашим именем пользователя GitHub

    ```shell
    git clone https://github.com/ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ/freeCodeCamp.git
    ```

Это загрузит весь репозиторий freeCodeCamp в вашу директорию проекта.

## Установка `главного` репозитория

Теперь, когда вы загрузили вашу копию, вам нужно установить `главный` репозиторий.

Как упоминалось ранее, репозиторий по адресу `https://github.com/freeCodeCamp/freeCodeCamp` зачастую называют `главным` репозиторием. Ваша копия по адресу `https://github.com/ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ/freeCodeCamp` зачастую называется `источником` для других репозиториев.

Вам нужно создать локальнй клон для `главного` репозитория в дополнение к `источнику`. Это позволит синхронизировать изменения из главного репозитория. Таким образом, вам удастся избежать повторного копирования и клонирования снова и снова.

1. Измените текущую директорию на директорию freeCodeCamp:

    ```shell
    cd freeCodeCamp
    ```

2. Добавьте удаленное соединение с главным репозиторием freeCodeCamp:

    ```shell
    git remote add upstream https://github.com/freeCodeCamp/freeCodeCamp.git
    ```

3. Убедитесь, что конфигурация выглядит хорошо:

    ```shell
        git remote -v
    ```

        Выход должен быть чем-то вроде этого:

    ```shell
        origin    https://github.com/YOUR_USER_NAME/freeCodeCamp.git (fetch)
        origin    https://github.com/YOUR_USER_NAME/freeCodeCamp.git (push)
        upstream    https://github.com/freeCodeCamp/freeCodeCamp.git (fetch)
        upstream    https://github.com/freeCodeCamp/freeCodeCamp.git (push)
    ```

## Running freeCodeCamp locally on your machine

Now that you have a local copy of freeCodeCamp, you can follow these instructions to get it running locally. This will help you to:

- Preview edits to pages as it would appear on the learning platform.
- Work on UI related issues and enhancements.
- Debug and fix issues in the application servers and client apps.

You can skip running freeCodeCamp locally, if you are just editing files, doing a `rebase` or resolving `merge` conflicts. You can always return to this part of the instructions later.

[Skip running freeCodeCamp locally](#making-changes-to-your-clone-of-freecodecamp-locally)

### Installing prerequisites

Start by installing these prerequisite software.

| Prerequisite                                | Version | Notes |
| ------------------------------------------- | ------- | ----- |
| [MongoDB Community Server](https://docs.mongodb.com/manual/administration/install-community/) | `3.6`   | [Release Notes](https://docs.mongodb.com/manual/release-notes/), Note: We currently on `3.6`, an [upgrade is planned](https://github.com/freeCodeCamp/freeCodeCamp/issues/18275).
| [Node.js](http://nodejs.org)                | `8.x`   | [LTS Schedule](https://github.com/nodejs/Release#release-schedule) |
| npm (comes bundled with Node)               | `6.x`   | Does not have LTS releases, we use the version bundled with Node LTS |

**Important:**

We highly recommend updating to the latest stable releases a.k.a Long Term Support (LTS) versions of the above.
If Node.js or MongoDB is already installed on your machine, run the following commands to validate the versions:

```shell
node -v
mongo --version
npm -v
```

> If you have a different version, please install the recommended version. We can support installation issues for recommended versions only.

**I am having issues with installing the recommended Prerequisites. What should I do?**

We regularly develop on popular and latest operating systems like macOS 10.12 or later, Ubuntu 16.04 or later and Windows 10. Its recommended to lookup your specific issue on resources like: Google, Stack Overflow or Stack Exchange. Chances are that someone has faced the same issue and there is already an answer to your specific query.

If you are on a different OS, and/or are still running into issues, reach out to [contributors community on our public forum](https://www.freeCodeCamp.org/c/contributors) or the [Contributor's Chat room](https://gitter.im/freeCodeCamp/Contributors). We may be able to troubleshoot some common issues.

We can't support you on GitHub, because software installation issues are beyond the scope of this project.

### Installing dependencies

Start by installing the dependencies required for the application to startup.

```shell
# Install NPM dependencies
npm install
```

Then you need to add the private environment variables (API Keys):

```shell
# Create a copy of the "sample.env" and name it as ".env".
# Populate it with the necessary API keys and secrets:

# macOS / Linux
cp sample.env .env

# Windows
copy sample.env .env
```

The keys are not required to be changed, to run the app locally. You can leave the default values from the `sample.env` as it is.

`MONGOHQ_URL` is the most important one. Unless you have MongoDB running in a setup different than the defaults, the URL in the `sample.env` should work fine.

You can leave the other keys as they are. Keep in mind if you want to use more services you'll have to get your own API keys for those services and edit those entries accordingly in the `.env` file.

Next lets, bootstrap the various services, i.e. the api-server, the client UI application, etc. You can [learn more about these services in this guide](#).

By bootstrapping you are tying the links between the services. They are semi-independent. Meaning, in production these services are deployed to their own locations, but while running locally you want them all to be available to you.

```shell
# Bootstrap all projects inside this repository
npm run bootstrap
```

### Start MongoDB

You will need to start MongoDB, before you can start the application:

Start the MongoDB server in a separate terminal

- On macOS & Ubuntu:

    ```shell
    mongod
    ```

- On Windows, you have to instead specify the full path to the `mongod` binary

    Make sure to replace `3.6` with the version you have installed

    ```shell
    "C:\Program Files\MongoDB\Server\3.6\bin\mongod"
    ```

> ProTip:
> You can avoid having to start MongoDB every time, by installing it as a background service.
> You can [learn more about it in their documentation for your OS](https://docs.mongodb.com/manual/administration/install-community/)

### Seeding the database

Next, lets seed the database. In this step, we run the below command that will fill the MongoDB server with some initial data-sets that is required by the other services. This include a few schemas, among other things.

```shell
npm run seed
```

### Start the freeCodeCamp client application and API server

You can now start up the API server and the client applications.

```shell
npm run develop
```

This single command will fire up all the services, including the API server and the client applications available for you to work on.

Now open a web browser and visit <http://localhost:8000>. If the app loads, congratulations – you're all set.

> ProTip:
>
> The API Server serves APIs at `http://localhost:3000`
> The Gatsby app serves the client application at `http://localhost:8000`

Meaning, if you visit <http://localhost:3000/explorer> you should see the APIs that we have.

Congratulations 🎉! You now have a copy of freeCodeCamp's entire learning platform running on your local machine.

## Quick commands reference when working locally

[Here is a quick reference](/docs/README.md) to a list of commands that you may need locally from time to time:

## Making changes to your clone of freeCodeCamp locally

Next, you can make changes to files, and commit your changes.

Follow these steps:

1. Check that you are on the `master` branch

    ```shell
    git status
    ```

    You should get a output like this:

    ```shell
    On branch master
    Your branch is up-to-date with 'origin/master'.

    nothing to commit, working directory clean
    ```

    If you are not on master or your working directory is not clean, resolve any outstanding files/commits and checkout `master`:

    ```shell
    git checkout master
    ```

2. Next, you would want to `rebase` from the `upstream`.

    This step **will sync the lastest changes** from the main repository of freeCodeCamp. Its important that you rebase as often as possible, to avoid conflicts later.

    ```shell
    git pull --rebase upstream master
    ```

    You can optionally push this branch back to your origin, to have a clean history on your fork on GitHub.

    ```shell
    git push origin master --force
    ```

3. Next, you will have to create a fresh new branch.

    Working on a separate branch for every single issue, helps you keep your local work copy clean. You should never work on the `master`. This will soil your copy of freeCodeCamp and you may have to start over with a fresh clone or fork.

    Check that you are on `master` as explained previously, and branch off from there:

    ```shell
    git checkout -b fix/update-guide-for-xyz
    ```

    Your branch name should start with a `fix/`, `feat/`, etc. Avoid, using issue no.s in branches. Keep them short, meaningful and unique.

    Some examples of good branch names are:

    ```md
    fix/update-challenges-for-react
    fix/update-guide-for-html-css
    fix/platform-bug-sign-in-issues
    feat/add-guide-article-for-javascript
    translate/add-spanish-basic-html
    ```

4. Next, you can work on the editing pages and working on the code in your favorite text editor.

5. Once you are happy with the changes you should optionally run freeCodeCamp locally to preview the changes.

6. Make sure you fix any errors, and check the formating of your changes. We have style guide for the Guide articles and Coding challenges.

7. Next, check and confirm the files you are updating

    ```shell
    git status
    ```

    This should show a list of `unstaged` files that you have edited.

    ```shell
    On branch feat/documentation
    Your branch is up to date with 'upstream/feat/documentation'.

    Changes not staged for commit:
    (use "git add/rm <file>..." to update what will be committed)
    (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   CONTRIBUTING.md
        modified:   docs/README.md
        modified:   docs/how-to-setup-freecodecamp-locally.md
        modified:   docs/how-to-work-on-guide-articles.md
    ...
    ```

8. Stage the changes and make a commit.

    In this step you should only mark files that you have edited, or added. You can perform a reset, and resolve files that you did not intend to change.

    ```shell
    git add path/to/my/changed/file.ext
    ```

    Or, alternatively you can add all the `unstaged` files to the staging area:

    ```shell
    git add .
    ```

    Only the files that were moved to the staging area will added when you make a commit.

    ```shell
    git status
    ```

    Output:
    ```shell
    On branch feat/documentation
    Your branch is up to date with 'upstream/feat/documentation'.

    Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

        modified:   CONTRIBUTING.md
        modified:   docs/README.md
        modified:   docs/how-to-setup-freecodecamp-locally.md
        modified:   docs/how-to-work-on-guide-articles.md
    ```

    Now, you can commit your changes with a short message like so:

    ```shell
    git commit -m "fix: my short commit message"
    ```

    Some examples:

    ```md
    fix: update guide article for Java - for loop
    feat: add guide article for alexa skills
    ```

    Optional:

    We highly recommend making a conventional commit message. This is a good practice that you will see on some of the popular Open Source repositories. As a developer, this encourages you to follow standard practices.

    Some examples of conventional commit messages are:

    ```md
    fix: update HTML guide article
    fix: update build scripts for Travis-CI
    feat: add article for JavaScript hoisting
    docs: update contributing guidelines
    ```

    Keep these short, not more than 50 characters. You can always add additional information in the description of the commit message.

    This does not take any additional time than a unconventional message like 'update file' or 'add index.md'

    You can learn more about why you should use conventional commits [here](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#why-use-conventional-commits).

9. If you realise that you need to edit a file or, update the commit message after making a commit you can do so after editing the files with:

    ```shell
    git commit --amend
    ```

    This will open up a default, text editor like `nano` or `vi` where you can edit the commit message title and add/edit description.

10. Next, you can push your changes to your fork.

    ```shell
    git push origin branch/name-here
    ```

## Proposing a Pull Request (PR)

1. Once the edits have been committed, you will be prompted to create a pull request on your fork's GitHub Page.

    ![Image - Compare pull request prompt on GitHub](/docs/images/github/compare-pull-request-prompt.png)

2. By default, all pull requests should be against the freeCodeCamp main repo, `master` branch.

    Make sure that your Base Fork is set to freeCodeCamp/freeCodeCamp when raising a Pull Request.**

    ![Image - Comparing forks when making a pull request](/docs/images/github/comparing-forks-for-pull-request.png)

3. Submit the pull request from your branch to freeCodeCamp's `master` branch.

4. In the body of your PR include a more detailed summary of the changes you made and why.

    - You will be presented with a pull request template. This is a checklist that you should have followed before opening the pull request.

    - Fill in the details as they seem fit you. This information will be reviewed and decide whether or not, your pull request is going to be accepted.

    - If the PR is meant to fix an existing bug/issue then, at the end of
      your PR's description, append the keyword `closes` and #xxxx (where xxxx
      is the issue number). Example: `closes #1337`. This tells GitHub to
      automatically close the existing issue, if the PR is accepted and merged.

5. Indicate if you have tested on a local copy of the site or not.

    This is very important when you are making changes that are not copy editing markdown files. For example, changes to CSS or JavaScript code, etc.

## Get your PR accepted



## Getting Help

If you are stuck, and need help, let us know by asking in the ['Contributors' category on our forum](https://www.freecodecamp.org/forum/c/contributors) or the [Contributors chat room](https://gitter.im/FreeCodeCamp/Contributors) on Gitter.

There might be an error in the console of your browser or in Bash / Terminal / Command Line that will help identify the problem.

### Troubleshooting

If the app launches but you are encountering errors with the UI itself, for example if fonts are not being loaded or if the code editor is not displaying properly, you may try the following troubleshooting steps at least once:

```shell
# Remove all installed node modules
rm -rf node_modules ./**/node_modules

# Reinstall npm packages
npm install

# Bootstrap the project
npm run bootstrap

# Seed the database
npm run seed

# Re-start the application
npm run develop
```
