# useMemo Hook

useMemo memoizes the output of the function and not the function itself.
It helps optimize the app. It also helps with referential equality.

useEffect thinks that it receives a new dependency array or object everytime unless it receives a memoized value. When we use the useMemo hook, useEffect knows the dependency array has a referential equality and it's the same memoized value that was given before. So it renders faster.

```
 // const myArray = getArray();
  const myArray = useMemo(() => getArray(), []);

  useEffect(() => {
    console.log("New array");
  }, [myArray]);
```
