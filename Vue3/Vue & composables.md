
###### eg **Company Data:**

```
const languages: Languages[] = [Languages.German, ...];
const activeLanguage = ref(languages[0]);
function selectLanguage(language: Languages) {
  activeLanguage.value = language;
}
```

