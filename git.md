# โญ Git

## ๐ก Git์ด๋?
- Git์ `๋ถ์ฐ๋ฒ์ ๊ด๋ฆฌ์์คํ`์ผ๋ก `์ฝ๋์ ๋ฒ์ ์ ๊ด๋ฆฌ`ํ๋ ๋๊ตฌ์ด๋ค.
- 2005๋ ๋ฆฌ๋์ค ์ปค๋์ ์ํ ๋๊ตฌ๋ก ๋ฆฌ๋์ค ํ ๋ฅด๋ฐ์ค๊ฐ ๊ฐ๋ฐํ์๋ค.
- ์ปดํจํฐ ํ์ผ์ ๋ณ๊ฒฝ์ฌํญ์ ์ถ์ ํ๊ณ  ์ฌ๋ฌ ๋ช์ ์ฌ์ฉ์๋ค ๊ฐ์ ํด๋น ํ์ผ๋ค์ ์์์ ์กฐ์จ ๊ฐ๋ฅํ๋ค.
- ๋ฐ์ดํฐ๋ฅผ ํ์ผ ์์คํ์ ์ค๋์ท์ผ๋ก ๊ด๋ฆฌํ๊ณ  ๋งค์ฐ ํฌ๊ธฐ๊ฐ ์๋ค.
- ํ์ผ์ด ๋ฌ๋ผ์ง์ง ์์ผ๋ฉด ์ฑ๋ฅ์ ์ํด ํ์ผ์ ์๋ก ์ ์ฅํ์ง ์๋๋ค.

## ๐ก ๋ถ์ฐ๋ฒ์ ๊ด๋ฆฌ์์คํ(DVCS)
- ์ค์์ง์ค์๋ฒ์ ๊ด๋ฆฌ์์คํ์ ์ค์์์ ๋ฒ์ ์ ๊ด๋ฆฌํ๊ณ  ํ์ผ์ ๋ฐ์์ ์ฌ์ฉํ๋ค.
- ๋ฐ๋ฉด์ ๋ถ์ฐ๋ฒ์ ๊ด๋ฆฌ์์คํ์ ์๊ฒฉ ์ ์ฅ์(remote repository)๋ฅผ ํตํ์ฌ ํ์ํ๊ณ , ๋ชจ๋  ํ์คํ ๋ฆฌ๋ฅผ ํด๋ผ์ด์ธํธ๋ค์ด ๊ณต์ ํ๋ค.

## ๐ก Git ๊ธฐ๋ณธ ํ๋ฆ
1. ์์(์์ )ํ ํ์ผ์ Working directory์ ์์นํ๋ค.
2. 1๋ฒ์ ํ์ผ์ addํ์ฌ Staging area์ ๋ชจ์๋ค.
    - untracked / modified -> staged
3. ๋ชจ์ธ ํ์ผ์ commitํ์ฌ ๋ฒ์ ์ผ๋ก ๊ธฐ๋กํ๋ค.
    - staged -> committed

## ๐ก Git ๊ธฐ๋ณธ ๋ช๋ น์ด
- $ git init
  - ํน์  ํด๋๋ฅผ git ์ ์ฅ์(repository)๋ก ๋ง๋ค์ด git์ผ๋ก ๊ด๋ฆฌ
    - .git ํด๋๊ฐ ์์ฑ๋จ
    - git bash์์๋ (master) ๋๋ (main) ์ด๋ผ๋ ํ๊ธฐ๋ฅผ ํ์ธํ  ์ ์์
- $ git add ํ์ผ๋ช.ํ์ฅ์
  - working directory์์ ๋ณ๊ฒฝ ๋ด์ฉ์ staging area์ ์ถ๊ฐํ๊ธฐ ์ํด ์ฌ์ฉ
    - untracked ์ํ์ ํ์ผ์ staged๋ก ๋ณ๊ฒฝ
    - modified ์ํ์ ํ์ผ์ staged๋ก ๋ณ๊ฒฝ
  - git add . ์ ํ์ฌ ๋๋ ํ ๋ฆฌ์ ๋ชจ๋  ํ์ผ์ add 
- $ git commit -m '์ปค๋ฐ๋ฉ์์ง'
  - staged ์ํ์ ํ์ผ๋ค์ ์ปค๋ฐ์ ํตํด ๋ฒ์ ์ผ๋ก ๊ธฐ๋ก
  - SHA-1 ํด์๋ฅผ ์ฌ์ฉํ์ฌ 40์ ๊ธธ์ด์ ์ฒดํฌ์ฌ์ ์์ฑํ๊ณ , ์ด๋ฅผ ํตํด ๊ณ ์ ํ ์ปค๋ฐ์ ํ๊ธฐ
  - ์ปค๋ฐ ๋ฉ์์ง๋ ๋ณ๊ฒฝ์ฌํญ์ ๋ํ๋ผ ์ ์๋๋ก ๋ชํํ๊ฒ ์์ฑํด์ผ ํจ
- $ git status
  - git ์ ์ฅ์์ ์๋ ํ์ผ์ ์ํ๋ฅผ ํ์ธํ๊ธฐ ์ํ์ฌ ํ์ฉ
    - Untracked: ๋ฒ์ ์ผ๋ก ๊ด๋ฆฌ๋ ์  ์๋ ํ์ผ(์๋ก ๋ง๋  ๊ฒฝ์ฐ)
    - Tracked: ์ด์ ๋ถํฐ ๋ฒ์ ์ผ๋ก ๊ด๋ฆฌ๋๊ณ  ์๋ ํ์ผ
      - Unmodified: ์์ ๋์ง ์์ ํ์ผ, git status์ ๋ํ๋์ง ์์
      - Modified: Changes not staged for commit(์์ ๋์์ผ๋ staged ๋์ง ์์ ํ์ผ)
      - Staged: Changes to be committed(staged ๋์์ผ๋ commit ๋์ง ์์ ํ์ผ)
    - Nothing to commit, working tree clean: ์์(์์ )ํ ํ์ผ์ด ๋ชจ๋ ์ปค๋ฐ๋ ์ํ์ด๊ณ  ๋ณ๋์ ์์ ์ฌํญ ๋ํ ์๋ ์ํ
- $ git log
  - ํ์ฌ ์ ์ฅ์์ ๊ธฐ๋ก๋ ์ปค๋ฐ์ ์กฐํ
  - ๋ค์ํ ์ต์์ ํตํด ๋ก๊ทธ๋ฅผ ์กฐํํ  ์ ์์
    - $ git log -1
    - $ git log --online
    - $ git log -2 --online

## ๐ก Git ์ค์  ํ์ผ(config)
- ์ฌ์ฉ์ ์ ๋ณด(commit author): ์ปค๋ฐ์ ํ๊ธฐ ์ํด ๋ฐ๋์ ํ์
  - git config --global user.name "username"
  - git config --global user.email "my@email.com"
- ์ค์  ํ์ธ
  - git config -l
  - git config --global-l
  - git config user.name

## ๐ก GitHub ์๊ฒฉ์ ์ฅ์ ํ์ฉํ๋ ๋ฐฉ๋ฒ
1. GitHub์์ New Repository ์์ฑ
2. ์๊ฒฉ์ ์ฅ์์ URL์ ํ์ธ
    - ์์: https://github.com/Rilee-0320/TIL.git
3. ๋ก์ปฌ ์ ์ฅ์์ ์๊ฒฉ ์ ์ฅ์ ์ ๋ณด ์ค์ ํ๊ธฐ
    - \$ git remote add orgin <์๊ฒฉ์ ์ฅ์ URL>
    - ์ผ๋ฐ์ ์ผ๋ก ์๊ฒฉ์ ์ฅ์์๋ origin์ด๋ผ๋ ์ด๋ฆ์ ๋ถ์
4. ๋ก์ปฌ ์ ์ฅ์์ ๋ฒ์ ์ ์๊ฒฉ ์ ์ฅ์๋ก ๋ณด๋ด๊ธฐ
    - ์๊ฒฉ์ ์ฅ์๋ก ๋ก์ปฌ ์ ์ฅ์์ ๋ณ๊ฒฝ์ฌํญ(์ปค๋ฐ)์ ์ฌ๋ฆผ(push)
    - \$ git push <์๊ฒฉ์ ์ฅ์> <๋ธ๋์น>
    - \$ git push origin master
5. ์๊ฒฉ์ ์ฅ์๋ก๋ถํฐ ๋ณ๊ฒฝ๋ ๋ด์ญ์ ๋ฐ์์ค๊ธฐ
    - \$ git pull <์๊ฒฉ์ ์ฅ์> <๋ธ๋์น>
    - \$ git pull origin master
6. ์๊ฒฉ์ ์ฅ์ ํ๋ก์ ํธ ์์ํ๊ธฐ
    - $ git clone <์๊ฒฉ์ ์ฅ์ url> : ์๊ฒฉ์ ์ฅ์๋ฅผ ๋ณต์ ํ์ฌ ๊ฐ์ ธ์ด
    - cf. ์๊ฒฉ์ ์ฅ์์ ํ์ผ์ ๋ค์ด๋ก๋ ๋ฐ๋ ๊ฒ์ ์ต์  commit, push ๋ ํ์ผ๋ง ๊ฐ์ ธ์ฌ ๋ฟ ๊ทธ ์ด์ ์ ๋ฒ์  ๊ธฐ๋ก๊น์ง ๊ฐ์ ธ์ค์ง ์์
    - cf. clone์ ์๊ฒฉ์ ์ฅ์๋ฅผ ๋ณต์ ํ๋ ๊ฒ์ด๋ pull์ ์๊ฒฉ์ ์ฅ์์ ์ปค๋ฐ๋ง์ ๊ฐ์ ธ์ด

### ๊ธฐํ ๋ช๋ น์ด
- git remote -v : ์๊ฒฉ์ ์ฅ์ ์ ๋ณด ํ์ธ
- git remote rm <์๊ฒฉ์ ์ฅ์> : ์๊ฒฉ์ ์ฅ์ ์ญ์ 

## ๐ก .gitignore
- ๊ฐ๋ฐ ํ๋ก์ ํธ์์ ๋ณ๋๋ก ๋ฒ์  ๊ด๋ฆฌ๋ฅผ ํ์ง ๋ง์์ผ ํ , ์ฆ ์ปค๋ฐํ์ง ์์ ํ์ผ, ๋๋ ํ ๋ฆฌ๊ฐ ๋ฐ์ํจ
- .gitignore ํ์ผ์ ์์ฑํ๊ณ  ํด๋น ํ์ผ๋ช ๋๋ ๋๋ ํ ๋ฆฌ๋ช์ ์๋ ฅํ  ๊ฒฝ์ฐ ํด๋น ํ์ผ, ๋๋ ํ ๋ฆฌ๋ฅผ ์ ์ธํ๊ณ  ์ปค๋ฐ ๊ฐ๋ฅ
- ์ฐธ๊ณ : [.gitignore.io](https://www.toptal.com/developers/gitignore/)

## ๐ก Git branch
- ๋๋ฆฝ์ ์ธ ์์ํ๋ฆ์ ๋ง๋ค๊ณ  ๊ด๋ฆฌํ๊ธฐ ์ํด branch ํ์ฉ
- ๋ธ๋์น ์ฃผ์ ๋ช๋ น์ด
  - (master) $ git branch {๋ธ๋์น๋ช} : ๋ธ๋์น ์์ฑ
  - (master) $ git checkout {๋ธ๋์น๋ช} : ๋ธ๋์น ์ด๋
  - (master) $ git checkout -b {๋ธ๋์น๋ช} : ๋ธ๋์น ์์ฑ ๋ฐ ์ด๋
  - (master) $ git branch : ๋ธ๋์น ๋ชฉ๋ก
  - (master) $ git branch -d {๋ธ๋์น๋ช} : ๋ธ๋์น ์ญ์ 
  - (master) $ git merge {๋ธ๋์น๋ช} : ๋ธ๋์น ๋ณํฉ

  ### Git branch ๋ณํฉ
  1. fast-foward : ๋ธ๋์น ์์ฑ๋ ์ดํ master ๋ธ๋์น์ ๋ณ๊ฒฝ ์ฌํญ์ด ์๋ ์ํฉ
      - ์์
      1. {feature/home} branch ์์ฑ ๋ฐ ์ด๋
        ```bash
        (master) $ git branch feature/home
        (master) $ git checkout feature/home
        ```
      2. ์์ ์๋ฃ ํ commit
        ```bash
        (feature/home) $ touch home.txt
        (feature/home) $ git add .
        (feature/home) $ git commit -m 'Add home.txt'
        (feature/home) $ git log --oneline
        b534a34 (HEAD -> feature/home) Complete Home!!!!
        e89616a (master) Init
        ```
      3. master ์ด๋
        ```bash
        (feature/home) $ git checkout master
        (master) $ git log --oneline
        ```
      4. master์ ๋ณํฉ
        ```bash
        (master) $ git merge feature/home 
        Updating e89616a..b534a34
        Fast-forward
          home.txt | 0
          1 file changed, 0 insertions(+), 0 deletions(-)
          create mode 100644 home.txt
        ```
      5. ๊ฒฐ๊ณผ : fast-foward
        ```bash
        (master) $ git log --oneline
        b534a34 (HEAD -> master, feature/home) Complete Home!!!!
        e89616a Init
        ```
      6. branch ์ญ์ 
        ```bash
        (master) $ git branch -d feature/home 
        Deleted branch feature/home (was b534a34).
        ```
  2. merge commit : ์๋ก ๋ค๋ฅธ ์ด๋ ฅ(commit)์ ๋ณํฉ(merge)ํ๋ ๊ณผ์ ์์ **๋ค๋ฅธ ํ์ผ์ด ์์ **๋์ด ์๋ ์ํฉ, git์ด auto merging์ ์งํํ๊ณ , **commit์ด ๋ฐ์**
      - ์์
      1. {feature/about} branch ์์ฑ ๋ฐ ์ด๋
        ```bash
        (master) $ git checkout -b feature/about
        (feature/about) $
        ```
      2. ์์ ์๋ฃ ํ commit
        ```bash
        (feature/about) $ touch about.txt
        (feature/about) $ git add .
        (feature/about) $ git commit -m 'Add about.txt'
        (feature/about) $ git log --oneline
        5e1f6de (HEAD -> feature/about) ์๊ธฐ์๊ฐ ํ์ด์ง ์๋ฃ!
        b534a34 (master) Complete Home!!!!
        e89616a Init
        ```
      3. master ์ด๋
        ```bash
        (feature/about) $ git checkout master
        (master) $
        ```
      4. *master์ ์ถ๊ฐ commit ๋ฐ์์ํค๊ธฐ!!*
        * **๋ค๋ฅธ ํ์ผ์ ์์  ํน์ ์์ฑํ์!**
        ```bash
        (master) $ touch master.txt
        (master) $ git add .
        (master) $ git commit -m 'Add master.txt'
        (master) $ git log --oneline
        98c5528 (HEAD -> master) ๋ง์คํฐ ์์....
        b534a34 Complete Home!!!!
        e89616a Init
        ```
      5. master์ ๋ณํฉ
        ```bash
        (master) $ git merge feature/about
        ```
      6. ๊ฒฐ๊ณผ -> ์๋์ผ๋ก *merge commit ๋ฐ์*
      7. ์ปค๋ฐ ๋ฐ ๊ทธ๋ํ ํ์ธํ๊ธฐ
        ```bash
        $ git log --oneline --graph
        *   582902d (HEAD -> master) Merge branch 'feature/about'
        |\
        | * 5e1f6de (feature/about) ์๊ธฐ์๊ฐ ํ์ด์ง ์๋ฃ!
        * | 98c5528 ๋ง์คํฐ ์์....
        |/
        * b534a34 Complete Home!!!!
        * e89616a Init
        ```
      8. branch ์ญ์ 
        ```bash
        $ git branch -d feature/about 
        Deleted branch feature/about (was 5e1f6de).
        ```
  3. merge commit ์ถฉ๋์๋ก ๋ค๋ฅธ ์ด๋ ฅ(commit)์ ๋ณํฉ(merge)ํ๋ ๊ณผ์ ์์ **๊ฐ์ ํ์ผ์ ๋์ผํ ๋ถ๋ถ์ด ์์ **๋์ด ์๋ ์ํฉ, git์ด auto merging์ ํ์ง ๋ชปํ๊ณ  ์ถฉ๋ ๋ฉ์์ง๊ฐ ๋ธ, ํด๋น ํ์ผ์ ์์น์ ํ์คํ์์ ๋ฐ๋ผ ํ์, ์ํ๋ ํํ์ ์ฝ๋๋ก ์ง์  ์์ ์ ํ๊ณ  ์ง์  commit์ ๋ฐ์ ์์ผ์ผ ํจ
      - ์์
      1. {feature/test} branch ์์ฑ ๋ฐ ์ด๋
        ```bash
        (master) $ git checkout -b feature/test
        ```
      2. ์์ ์๋ฃ ํ commit
        ```bash
        # README.md ํ์ผ ์ด์ด์ ์์ 
        (feature/test) $ touch test.txt
        (feature/test) $ git add .
        (feature/test) $ git commit -m 'Add test.txt'
        (feature/test) $ git log --oneline
        95fad1c (HEAD -> feature/test) README ์์ ํ๊ณ  test ์์ฑํ๊ณ 
        582902d (master) Merge branch 'feature/about'
        98c5528 ๋ง์คํฐ ์์....
        5e1f6de ์๊ธฐ์๊ฐ ํ์ด์ง ์๋ฃ!
        b534a34 Complete Home!!!!
        e89616a Init
        ```
      3. master ์ด๋
        ```bash
        $ git checkout master
        ```
      4. *master์ ์ถ๊ฐ commit ๋ฐ์์ํค๊ธฐ!!*
        * **๋์ผ ํ์ผ์ ์์  ํน์ ์์ฑํ์!**
        ```bash
        # README.md ํ์ผ ์ด์ด์ ์์ 
        (master) $ git add README.md
        (master) $ git commit -m 'Update README.md'
        ```
      5. master์ ๋ณํฉ
        ```bash
        (master) $ git merge feature/test 
        Auto-merging README.md
        CONFLICT (content): Merge conflict in README.md
        Automatic merge failed; fix conflicts and then commit the result.
        ```
      6. ๊ฒฐ๊ณผ -> *merge conflict๋ฐ์*
        > git status ๋ช๋ น์ด๋ก ์ถฉ๋ ํ์ผ์ ํ์ธํ  ์ ์์
        ```bash
        (master|MERGING) $ git status
        On branch master
        You have unmerged paths.
          (fix conflicts and run "git commit")        
          (use "git merge --abort" to abort the merge)
        
        Changes to be committed:
                new file:   test-1.txt
                new file:   test-2.txt
                new file:   test.txt
        
        Unmerged paths:
          (use "git add <file>..." to mark resolution)
                both modified:   README.md
        ```
      7. ์ถฉ๋ ํ์ธ ๋ฐ ํด๊ฒฐ

        ```
        <<<<<<< HEAD
        # ๋ง์คํฐ์์ ์์ํจ...
        =======
        # ํ์คํธ์์ ์์ฑ
        >>>>>>> feature/test
        ```
      8. merge commit ์งํ
        ```bash
        (master|MERGING) $ git add .
        (master|MERGING) $ git commit
        ```
        * vim ํธ์ง๊ธฐ ํ๋ฉด์ด ๋ํ๋จ
          * ์๋์ผ๋ก ์์ฑ๋ ์ปค๋ฐ ๋ฉ์์ง๋ฅผ ํ์ธํ๊ณ , `esc`๋ฅผ ๋๋ฅธ ํ `:wq`๋ฅผ ์๋ ฅํ์ฌ ์ ์ฅ ๋ฐ ์ข๋ฃํจ
          * `w` : write
          * `q` : quit

        * vs code ํธ์ง๊ธฐ์์ ๋ฉ์์ง๋ณด๊ณ  ๋ซ์์ฃผ์!
      9. ์ปค๋ฐ ๋ฐ ํ์ธํ๊ธฐ

        ```bash
        (master) $ git log --oneline --graph
        *   bc1c0cd (HEAD -> master) Merge branch 'feature/test'
        |\  
        | * 95fad1c (feature/test) README ์์ ํ๊ณ  test ์์ฑํ๊ณ 
        * | 2ecad28 ๋ฆฌ๋๋ฏธ ์์ 
        |/  
        *   582902d Merge branch 'feature/about'
        |\  
        | * 5e1f6de ์๊ธฐ์๊ฐ ํ์ด์ง ์๋ฃ!
        * | 98c5528 ๋ง์คํฐ ์์....
        |/  
        * b534a34 Complete Home!!!!
        * e89616a Init
        ```
      10. branch ์ญ์ 
        ```bash
        (master) $ git branch -d feature/test
        ```

## ๐ก Git Flow
- Git์ ํ์ฉํ์ฌ ํ์ํ๋ ํ๋ฆ์ผ๋ก branch๋ฅผ ํ์ฉํ๋ ์ ๋ต
- ๊ฐ์ ๋๋ฆฝ๋ ๋ฒ์ ์ ํ๋ฆ์ ๋ง๋ค ์ ์์

### GitHub Flow ๊ธฐ๋ณธ ์์น
1. master branch๋ ๋ฐ๋์ ๋ฐฐํฌ ๊ฐ๋ฅํ ์ํ์ฌ์ผ ํ๋ค.
2. feature branch๋ ๊ฐ ๊ธฐ๋ฅ์ ์๋๋ฅผ ์ ์ ์๋๋ก ์์ฑํ๋ค.
3. commit message๋ ๋งค์ฐ ์ค์ํ๋ฉฐ, ๋ชํํ๊ฒ ์์ฑํ๋ค.
4. Pull Request๋ฅผ ํตํด ํ์์ ์งํํ๋ค.
5. ๋ณ๊ฒฝ ์ฌํญ์ ๋ฐ์ํ๊ณ  ์ถ๋ค๋ฉด master branch์ ๋ณํฉํ๋ค.

### GitHub Flow Models
1. Shared Repository Model
  - ๋์ผํ ์ ์ฅ์๋ฅผ ๊ณต์ ํ์ฌ ํ์ฉํ๋ ๋ฐฉ์
  - ํ์์ collaborator๋ก ๋ฑ๋กํ๊ณ  ์ด๋ํ์ฌ ๋์ผํ ์ ์ฅ์๋ฅผ clone ํ์ฌ ์์
  - ๋ธ๋์น์์ ์์ํ๊ณ  GitHub์ผ๋ก Push
    - ํญ์ ๋๋ฆฝ์ ์ธ feature branch์์ ์์
    - Commit์ผ๋ก ์์์ ์ด๋ ฅ์ ๋จ๊น
    - ์์ฑ๋ ์ฝ๋๋ ์๊ฒฉ ์ ์ฅ์๋ก push ํจ
  - Pull Request ์์ฑ ๋ฐ Review, Merge
    - GitHub์์ Pull Request ๋ฒํผ์ ๋๋ฅด๊ณ  ์์ฒญ์ ์์ฑ
    - ๊ด๋ฆฌ์๋ ์์ฑ๋ ์ฝ๋๋ฅผ ํ์ธ ํ ๋ณํฉ
2. Fork & Pull Model
  - Repository์ Collaborator๋ก ๋ฑ๋ก๋์ง ์์ ์ํ์์ ์งํ
  - GitHub ๊ธฐ๋ฐ์ ์คํ์์ค ์ฐธ์ฌ ๊ณผ์ ์์ ์ฐ์ด๋ ๋ฐฉ์
  - ์๊ฒฉ ์ ์ฅ์๋ฅผ fork ํ ํ ๋ด ์ ์ฅ์๋ก ๋ณต์ ๋ณธ์ ๊ฐ์ ธ์จ ๋ค ๋ก์ปฌ์์ ์์ ํ ์๊ฒฉ ์ ์ฅ์๋ก push ๊ฐ๋ฅ

## ๐ก Git ๊ด๋ จ ์ฐธ๊ณ ์๋ฃ
- [๋๊ตฌ๋ ์ฝ๊ฒ ์ดํดํ  ์ ์๋ Git](https://backlog.com/git-tutorial/kr/)
- [Pro Git](https://git-scm.com/book/ko/v2)
- [์ข์ git commit ๋ฉ์์ง๋ฅผ ์ํ ์์ด ์ฌ์ ](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)
- [์ข์ git ์ปค๋ฐ ๋ฉ์์ง๋ฅผ ์์ฑํ๊ธฐ ์ํ 7๊ฐ์ง ์ฝ์](https://meetup.nhncloud.com/posts/106)