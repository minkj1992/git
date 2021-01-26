# How to re-merge from reverted branch
> 해결법: https://stackoverflow.com/a/55936184


## 상황
> 브랜치 이름은 임의로 지정한 것 입니다.

- master
- feature/v1-a
- feature/v2-a

이렇게 총 3개의 브랜치가 있었다. github-flow전략을 사용하고 있었기 때문에, feature/v1-a를 완료한 시점에 push 후, master로 merge 시켰지만, v2 스펙이 들어가 있었기 때문에, 이후 v2에 다시 넣기로 하고, revert를 시켰다.

그후 revert된 commit을 가지고 있는 마스터로 부터, feature/v2-a를 받아서 간단한 작업을 했고 v2를 적용하기 위해 master로 push하려했는데, 여기서 문제 **feature/v1-a에 들어있는 v2 기능들을 사용하고 싶다**는 니즈가 있었다. 

그러나 아무리 시도해도, 아래와 같은 상황이 발생한다. 

```bash
 * branch            feature/ver-middleware -> FETCH_HEAD

Already up to date.
```

왜냐하면 기존에 revert되었더라도 merge되었다고 커밋으로 기록이 남아있기 때문에.. 

**아무래도 다음부터 revert할때는 reset하는 방향으로 작업 고려해봐야겠다. **