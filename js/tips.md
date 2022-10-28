# JS Tips

### Use prettier code formatting for JS/JSX accross the project (avoiding .node_modules and .next files) in bash way
```
find . -type f -name "*.jsx" -o -name "*.js" -not  -path "./node_modules/*" -prune -not -path "./.next/*" -prune -exec prettier {} -w \;
```
