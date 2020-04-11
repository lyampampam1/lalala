## Homework in Laboratory work II

### Part I

- [x] 1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
 ```sh
 https://github.com/Robert29000/timp-lab-02
 ```
- [x] 2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
 ```sh
 ~ $ mkdir timp-lab-02
 ~/timp-lab-02 $ echo "# timp-lab-02" >> README.md
 ~/timp-lab-02 $ git init
 ~/timp-lab-02 $ git add README.md
 ~/timp-lab-02 $ git commit -m "first commit"
 ~/timp-lab-02 $ git remote add origin 
 ~/timp-lab-02 $ git push -u origin master
 ```
- [x] 3. Создайте файл `Hello world.cpp` в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку `using namespace std;`.
 ```sh
 ~/timp-lab-02 $ cat > "Hello world.cpp" << EOF
 #include <iostream>
 
 using namespace std;
 int main(int argc, char** argv){
  cout << "Hello world" << endl;
 }
 EOF
 ```
- [x] 4. Добавьте этот файл в локальную копию репозитория.
 ```sh
 ~/timp-lab-02 $ git add "Hello world.cpp"
 ```
- [x] 5. Закоммитьте изменения с *осмысленным* сообщением.
 ```sh
 ~/timp-lab-02 $ git commit -m "Added new cpp file"
 ```
- [x] 6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение `Hello world from @name`, где `@name` имя пользователя.
 ```sh
  ~/timp-lab-02 $ alias edit=subl
  ~/timp-lab-02 $ edit "Hello world.cpp"
  #include <iostream>
  #include <string>
  
  using namespace std;
  int main(int argc, char** argv){
   string name;
   cin >> name;
   cout << "Hello world from " << name << endl;
  }
 ```
- [x] 7. Закоммитьте новую версию программы. Повторно писать команду `git add` не надо, т.к. файл уже был добавлен в шаге **4**.
 ```sh
 ~/timp-lab-02 $ git commit -a -m "Changed cpp file"
 ```
- [x] 8. Запуште изменения в удалёный репозиторий.
 ```sh
 ~/timp-lab-02 $ git push -u origin master
 ```
- [x] 9. История коммитов доступна в удалёном репозитории.

### Part II

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
- [x] 1. В локальной копии репозитория создайте локальную ветку `patch1`.
 ```sh
 ~/timp-lab-02 $ git checkout -b patch1
 ```
- [x] 2. Внесите изменения в ветке `patch1` по исправлению кода и избавления от `using namespace std;`.
 ```sh
 ~/timp-lab-02 $ edit "Hello world.cpp"
 #include <iostream>
 #include <string>
  
 int main(int argc, char** argv){
  string name;
  std::cin >> name;
  std::cout << "Hello world from " << name << std::endl;
 }
 ```
- [x] 3. **commit**, **push** локальную ветку в удалённый репозиторий.
 ```sh
 ~/timp-lab-02 $ git commit -a -m "Fixed cpp file"
 ~/timp-lab-02 $ git push -u origin patch1
 ```
- [x] 4. Ветка `patch1` доступна в удалёный репозитории.
- [x] 5. Создадим pull-request `patch1 -> master`.
- [x] 6. В локальной копии в ветке `patch1` добавьте в исходный код комментарии.
 ```sh
 ~/timp-lab-02 $ edit "Hello world.cpp"
 #include <iostream>
 #include <string>
  
 int main(int argc, char** argv){
  string name; \\ User name
  std::cin >> name; \\ Input user name
  std::cout << "Hello world from " << name << std::endl;
 } 
 ```
- [x] 7. **commit**, **push**.
 ```sh
 ~/timp-lab-02 $ git commit -a -m "Added comments"
 ~/timp-lab-02 $ git push -u origin patch1
 ```
- [x] 8. Новые изменения есть в созданном на **шаге 5** pull-request
- [x] 9. В удалённый репозитории выполните  слияние PR `patch1 -> master` и удалите ветку `patch1` в удаленном репозитории.
- [x] 10. Локально выполните **pull**.
 ```sh
 ~/timp-lab-02 $ git pull origin
 ```
- [x] 11. С помощью команды **git log** просмотрите историю в локальной версии ветки `master`.
 ```sh
 ~/timp-lab-02 $ git log
 ```
- [x] 12. Удалите локальную ветку `patch1`.
 ```sh
 ~/timp-lab-02 $ git branch -d patch1
 ```

### Part III

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. Создайте новую локальную ветку `patch2`.
2. Измените *code style* с помощью утилиты [**clang-format**](http://clang.llvm.org/docs/ClangFormat.html). Например, используя опцию `-style=Mozilla`.
3. **commit**, **push**, создайте pull-request `patch2 -> master`.
4. В ветке **master** в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
5. Убедитесь, что в pull-request появились *конфликтны*.
6. Для этого локально выполните **pull** + **rebase** (точную последовательность команд, следует узнать самостоятельно). **Исправьте конфликты**.
7. Сделайте *force push* в ветку `patch2`
8. Убедитель, что в pull-request пропали конфликтны. 
9. Вмержите pull-request `patch2 -> master`.

## Links

- [hub](https://hub.github.com/)
- [GitHub](https://github.com)
- [Bitbucket](https://bitbucket.org)
- [Gitlab](https://about.gitlab.com)
- [LearnGitBranching](http://learngitbranching.js.org/)

```
Copyright (c) 2015-2020 The ISC Authors
```