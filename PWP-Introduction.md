test

```excel
=ARRAYFORMULA(
if(B2:B ="" ,
  "",
  IF(C2:C="", "<h2" & B2:B & "</h2>" &  CHAR(10) & "<p>" & B2:B & "</p>", 
    IFERROR("<h2" & B2:B & "</h2>" &  CHAR(10) & "<p>" & B2:B & "</p>" & REGEXREPLACE(C2:C, "(<h2.*?<\/h2>|<h1.*?<\/h1>)", "") , "<h2" & B2:B & "</h2>" &  CHAR(10) &"<p>" & B2:B & "</p>" & REGEXREPLACE(C2:C, "(<h2.*?<\/h2>|<h1.*?<\/h1>)", "") & D2))
)
)
```

