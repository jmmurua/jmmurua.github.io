# First steps

Open Rstudio like any other program. You will see 3 panels. The left panel corresponds to the console. In the bottom portion of this panel you will see the symbol ">". This is the command line and is where you write the commands. To run a command, that is, for the computer to execute the command, you must press enter. Once the computer has finish to process the command, the result will be displayed in the console panel.

## Using the console

Look what happens if you write 1 + 1

```{r, echo=TRUE}
1 + 1

```

If you look closely, the result is not only the number 2, it is preceded by a [1]. This has more sense when the output is a series of elements shown in rows. To clarify this, enter the command 50:100 to the console.

```{r}
50:100
```

Basically, the number in square brackets shows you that a given line starts with the Nth component of the series. The first line starts with the first component, the second line starts with the 20th, and the third with the 39th. You will learn more about this in the section "[Subsets of an object]"

The operator ":" is used to obtain all the integers between two integers. The result is a one by one sequence, from the first to the last integer. 

In the console you can use the up arrow in your keyboard to see commands that were run in the past in your current R session.

