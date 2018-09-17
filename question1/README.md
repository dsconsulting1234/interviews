
# Question 1

In this question, we ask all candidates to do **Section A** and then you
have your choice of doing **Section B** or **Section C**.

Ambitious full-stack engineers may do all three.  :)


## A.  Fibonacci Numbers

## Write a function `fib(n)` that takes an integer `n` as input and returns the `n`th Fibonacci number.

Recall that Fibonacci numbers are a sequence of integers where each number in the sequence
is the sum of the previous two.

We begin with:

```
0 1
```

...and then `0 + 1 = 1`, so:

```
0 1 1
```

...and `1 + 1 = 2`:

```
0 1 1 2
```

Ex:

```
>>> fib(0)
0
>>> fib(1)
1
>>> fib(2)
1
>>> fib(3)
2
```

There's more than one approach to solving this problem.

Choose your favorite and implement that, but be prepared to
compare/contrast different approaches, (dis)advantages of each.

Hint: How could you optimize this if this function was called
repeatedly and for larger values?  Ex:  `fib(1000)` and then
`fib(2000)`.


## B.  Turn Your Function Into A REST Web Service Call

Using [Python Flask](http://flask.pocoo.org/ "Flask Homepage"),
implement your solution to **Section A** as a REST web service call
that returns a JSON response.

Ex:

(in one terminal)
```
$ FLASK_APP=fib.py flask run
 * Serving Flask app "fib.py"
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/0 HTTP/1.1" 200 -
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/1 HTTP/1.1" 200 -
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/2 HTTP/1.1" 200 -
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/3 HTTP/1.1" 200 -
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/4 HTTP/1.1" 200 -
127.0.0.1 - - [17/Sep/2018 14:46:07] "GET /fib/5 HTTP/1.1" 200 -
```

(and in another terminal)
```
$ for i in `seq 0 5`; do curl http://127.0.0.1:5000/fib/$i ; done
{"result":0}
{"result":1}
{"result":1}
{"result":2}
{"result":3}
{"result":5}
```

This is a trivial example, but be prepared to discuss the request and
response sequence in detail.  We can use this example as a
conversation piece for how to build web services, API design, how
parameters should work...

## C.  Make A Simple Angular 2+ App That Uses the `/fib` REST Web Service Call

NOTE: For this exercise, you don't need to build the actual web
service (unless you want to), you can mock it with
`'angular-in-memory-web-api'`.

You should also feel free to [use StackBlitz to make life easier](https://stackblitz.com "StackBlitz website").

