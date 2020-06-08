To run ccls on QMK, you need to tell ccls flags to run with and place them in .ccls file
To do this run:
```sh
qmk compile
echo 'clang' > .ccls; cat .build/obj_<build directory>/cflags.txt | sed 's/ -/\n-/g' | sed 's/ //' | sed 's/ *$//' >> .ccls
```

For example
```sh
echo 'clang' > .ccls; cat .build/obj_planck_ez_rcarriga/cflags.txt | sed 's/ -/\n-/g' | sed 's/ //' | sed 's/ *$//' >> .ccls
```

Source: https://www.reddit.com/r/olkb/comments/bhdzxe/has_anyone_got_a_c_language_server_working_with/elur31t/
