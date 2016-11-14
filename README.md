## 源自:
```bash
https://github.com/ruanyf/fortunes.git
```

## Screenshot

![](./screenshot.png)

## Usage

```bash
$ fortune [OPTIONS] [/path/to/fortunes]
```

Options

```
- -c     Show the cookie file from which the fortune came.
- -f     Print out the list of files which would be searched, but don't print a fortune.
- -e     Consider all fortune files to be of equal size.
```

Example of `-c`

```bash
$ fortune -c

(fortunes)
%
"Don't waste life in doubts and fears."
  ~Ralph Waldo Emerson
```

Example of `-f`

```bash
$ fortune -f

100.00% /usr/share/games/fortunes
     0.03% ascii-art
    98.42% chinese
     0.36% song100
     1.19% tang300
```

Example of `-e`

```bash
$ fortune -e chinese fortunes
#  is equivalent to
$ fortune 50% chinese 50% fortunes

$ fortune -e chinese fortunes tang300 song100
#  is equivalent to
$ fortune 25% chinese 25% fortunes 25% tang300  25% song100
```

## How to automatically launch fortune when opening a shell window

Depending on which shell you use, at the end of your `~/.bashrc` or `~/.zshrc` file, copy the following lines into it.

```bash
alias fortune-ch='fortune 55% tang300 25% song100 5% ascii-art chinese'
```

## How to make your own fortune database file

(1) Write your fortune items into a file.

(2) Append a percent sign (%) after each item. The percent sign should take a new line. The following is an example.

```
A day for firm decisions!!!!!  Or is it?
%
A few hours grace before the madness begins again.
%
A gift of a flower will soon be made to you.
%
A long-forgotten loved one will appear soon.

Buy the negatives at any price.
%
A tall, dark stranger will have more fun than you.
```

(3) Generate the index file.

```bash
strfile -c % your-fortune-file your-fortune-file.dat
```

(4) Move the fortune file and its index file into `/usr/share/games/fortunes/`.