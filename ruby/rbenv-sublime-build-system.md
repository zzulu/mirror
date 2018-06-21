# rbenv Build System On Sublime Text

rbenv를 이용해서 ruby를 설치를 한 경우에는, Sublime Text의 build가 안되는 경우가 있다. Sublime의 build는 시스템 ruby를 사용하기 때문에 ruby가 설치되어있지 않은 경우에는 build가 되지 않고, 설치가 되어 있더라도 rbenv를 통해서 설치하면 rbenv의 ruby로 build 하도록 경로를 따로 잡아주어야 한다.

아래의 코드로 `rbenv.sublime-build`라는 이름의 새로운 build system을 만들어 주자.

```json
{
  "cmd": ["/home/[username]/.rbenv/shims/ruby", "$file"],
  "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
  "selector": "source.ruby"
}
```
