# rev-list

> 모든 커밋(브랜치들 포함)들에 대해, 키워드로 검색 가능

- IDCARD 라는 키워드로 모든 커밋 검색

```bash
$ git rev-list --all --branches | xargs git grep "IDCARD"
```

- 커밋 id를 통해 branch 알아내기

```bash
git show 1253d0819099b4be3f1ac5e77d003daee5379173
```
