# Output Examples

## General Interview

Raw:

```text
[00:15] **[Speaker 0]**: 呃，你们在北美市场的策略是什么呀？
[00:18] **[Speaker 1]**: 嗯，对，我们主要是切那个西语人群嘛，就是这个群体在美国其实是被严重低估的。
[00:25] **[Speaker 1]**: 嗯，就是目前DAU已经到了50万了嘛，主要来自那个墨西哥裔社区。
[00:32] **[Speaker 1]**: 对对对，然后我们判断就是这个其实是比那个主流英语市场更容易建立壁垒的一个切入点。
[00:40] **[Speaker 0]**: 哦，那融资情况怎么样？
[00:42] **[Speaker 1]**: 呃，目前就是完成了1200万美元的A轮嘛。
```

Cleaned:

```markdown
- <font color="#3357D9">你们在北美市场的策略是什么？</font>
  - 我们主要切西语人群，这个群体在美国其实是被严重低估的。
  - 目前 DAU 已经到了 50 万，主要来自墨西哥裔社区。
  - **我们判断这是比主流英语市场更容易建立壁垒的切入点。**
- <font color="#3357D9">融资情况怎么样？</font>
  - 目前完成了 1200 万美元的 A 轮。
```

## Investment Interview With Follow-Up

Raw:

```text
[15:22] **[Speaker 0]**: 你们现在留存数据怎么样？
[15:25] **[Speaker 1]**: 嗯，对，我们测试版大概两千个用户嘛，然后呃次留是百分之八十多，然后七日留存是百分之六十，三十日留存是百分之五十。
[15:35] **[Speaker 1]**: 对对，然后就是最有意思的一点是到现在这些内容我们已经停更了，但是还有大概百分之四十的日活。
[15:42] **[Speaker 0]**: 哦，就是那两千个人里面现在还有八百个人每天还会看？
[15:45] **[Speaker 1]**: 对对对，我觉得这个数据是比较有说服力的。
```

Cleaned:

```markdown
- <font color="#3357D9">你们现在留存数据怎么样？</font>
  - 我们测试版大概两千个用户，次留是百分之八十多，七日留存是百分之六十，三十日留存是百分之五十。
  - **最有意思的一点是到现在这些内容我们已经停更了，但是还有大概百分之四十的日活。**
  - （<font color="#3357D9">就是那两千个人里面现在还有八百个人每天还会看？</font>）对，我觉得这个数据是比较有说服力的。
```

In this example, every retention data point is preserved individually. The follow-up is blue, parenthetical, and kept inside the same answer block.
