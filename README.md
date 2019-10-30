# git aliases

## git status
- zobrazi aktualny stav branche
```bash
alias gitst="git status"
```
- pripravi zmeny na commit
## git add
```bash
alias gitaa="git add -A ."
```
## git reset
- vrati svoje nove zmeny nad repozitarom na stav up to date nepouzivať dva krat po sebe lebo sa začneš presuvať stale o jeden commit spať
```bash
alias gitrh="git reset --hard"
```
- zmazanie jedneho nepushnuteho pripraveneho commitu
```bash
alias gitrh="git reset --hard HEAD^" # git reset --hard HEAD^1
```
- ak som pushol commit do repositara a chcem ho vratiť späť ->`git cm "message"` -> `git puf`
```bash
alias gitrsh="git reset --soft HEAD~" # git reset --soft HEAD~1
```
## checkout
- vrati ma na predoslu branchu kde som bol pred tym
```bash
alias gitco-="git checkout -"
```
- presunie ma na inu branchu
```bash
alias gitco="git checkout" # git checkout "nazov_branche"
```
- vytvori novu branchu a presunie ma tam
```bash
alias gitcob="git checkout -b" # git checkout -b "nazov_branche"
```
## merge
- vies mergnut vsetky zmeny vramci napr. develop branche do master branche alebo tvojej vytvorenej branche do mastra
```bash
alias gitm="git merge" # git merge develop master ||| git merge "nazov_tvojej_branche" master
```
## commit
- vytvorenie commitu musis definovat nazov commitu
```bash
alias gitcm="git commit -m" # git commit -m "nazov_commitu"
```
- ked chces do definovaneho commit vlozit dalsie upravy musis definovat cislo o kolko komitov chces urobit zmeny
```bash
alias gitcf="git commit --fixup" # git commit --fixup 1 -> git rebiad -> git ca -> git puf
```
- zaslem zmenu do predosleho commitu 
```bash
alias gitcan="git commit --amend --no-edit"
```
- zmena nazvu predosleho commitu zaslem zmenu do predosleho commitu a mozem zmenit nazov commitu môžem aj hneď definovať novy nazov 
```bash
alias gitcam="git commit --amend -m" # git commit --amend -m "novy_nazov_commitu"
```
## cherry-pick
- skopiruje zmeny z ktorehokolvek pushnuteho commitu je nutne definovat hash commitu
```bash
alias gitcp="git cherry-pick" # git cherry-pick "1dd68ba"
```
## push
- pushnem vsetky zmeny do repositara
```bash
alias gitpu="git push"
```
- pushnem vsetky zmeny do repositara na silu vacsinou sa to pouziva po gitca alebo po upravach rebasu
```bash
alias gitpuf="git push -f"
```
- tento prikaz je nutne pouziť ak si vytvoriš novu vetvu teda branchu a chceš ju pushnuť do orgiin aby ju videli aj kolegovia ale nechces ju pushnuť do mastra alebo develop branche
```bash
alias gitpus="git push -u origin HEAD"
```
## stash
- ulozim si docasne zmeny bez pushu
```bash
alias gitstm="git stash save" # git stash save "nazov_ulozeneho_stashu"
```
- prikas ti ukaze zoznam docasne ulozenych zmien lokalne u teba bez pushu
```bash
alias gitstl="git stash list"
```
- zmazem ulozeny stash pod svojim ulozenym nazvom
```bash
alias gitstd="git stash drop" # git stash drop "nazov_ulozeneho_stashu"
```
- chem na aktualnom mieste použiť zmeny zo stashu a nasledne ich zmazať zo stashu
```bash
alias gitstp="git stash pop" # git stash pop "nazov_ulozeneho_stashu"
```
## rebase
- pomocou tohto prikazu viem zapnut takzvany interaktivny mod, po spusteni sa otovori okno kde si mozem nastavit aku akciu chcem vykonat
```bash
alias gitrebi="git rebase -i"
```
- tymto prikazom chcem ukoncit interaktivny mod ale da sa vykonat ak su vsetky zmeny pushnute
```bash
alias gitrebc="git rebase --continue"
```
- vratit vsetky zmeny do povodneho stavu vramci interaktivneho modu
```bash
alias gitrebs="git rebase --skip"
```
## naopakovanejsie prikazy po sebe
- dostat aktualne zmeny do predosleho pushnuteho komitu
```bash
alias gitrw="git aa && gca && gpuf"
```
## lost commit
- kedze vramci gitovania nemozes nikdy nic stratit pomocou tychto prikazov sa vies pozriet aj na hladane zmeny a prepisane zmeny...
```bash
alias gitfh1="git fsck --lost-found"
alias gitfh2="git reflog"
```