# Boston Key Party CTF 2015: Brigham Circle

**Category:** School-Bus
**Points:** 25
**Solves** 
**Description:**

> Sanitization is hard, lets use regexp! : 25

## Write-up

When given an array as "input string", the [`ereg()`](http://php.net/manual/en/function.ereg.php) function will return `NULL`, which is not strictly equal to `FALSE`. This allows you to pass the [first check](https://github.com/ctfs/write-ups-2015/blob/8b5783df48c8cda99ceafb3dcdfabaefe4b9c9e7/boston-key-party-2015/school-bus/brigham-circle/52.10.107.64:8006/index.txt#L12).

Similarly, for the [`strpos()`](http://php.net/manual/en/function.strpos.php) function, the value `NULL` is returned, which is strictly inequal to `FALSE`. 
As a result, the [second check](https://github.com/ctfs/write-ups-2015/blob/8b5783df48c8cda99ceafb3dcdfabaefe4b9c9e7/boston-key-party-2015/school-bus/brigham-circle/52.10.107.64:8006/index.txt#L14) yields true when `$_GET['password']` is an array, i.e. when visiting `index.php?password[]=`.
This prints the flag: `OK_Maybe_using_rexpexp_wasnt_a_clever_move`.

## Other write-ups and resources

* none yet