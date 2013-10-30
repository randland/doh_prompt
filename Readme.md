To setup, clone this repo to your local computer. Make sure to make the say_doh script executable. Finally, in your .bash_profile, insert a call to say_doh where you determine the output after an error return code.

Sample .bash_profile prompt setup

```
### PROMPT SETUP ###
  # Colours
          RED="\[\033[0;31m\]"
        GREEN="\[\033[0;32m\]"
   COLOR_NONE="\[\e[0m\]"

  function prompt_func {
    previous_return_value=$?;
    if test $previous_return_value -eq 0
    then
      PS1="${GREEN}➜ ${COLOR_NONE} "
    else
      ~/dev/doh_prompt/say_doh
      PS1="${RED}➜ ${COLOR_NONE} "
    fi
  }

  PROMPT_COMMAND=prompt_func
```
