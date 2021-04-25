
### Regular Expression ???
```
stephen cole kleene, 1951 
grep, sed, awk
```

### Example
#### JIRA issue key ( EX : CI-100, NOWRAP-8670, JENKINS-200, SPACE : 1 )
```perl
my $target = 'NOWRAP-8670 : tested code commited';
my $match = $target =~ /([A-Z]*)-([1-9]?[0-9]*)/g;
```
