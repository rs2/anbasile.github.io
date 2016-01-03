#Tracking finances with emacs

I have a quick and dirty method for tracking my finances in emacs. It has tobe  easy to use otherwise you will give up using it.

## Create an org-capture template

    (setq org-capture-templates
        (quote (
	          ("f" "Finance" plain (file "~/git_private/stuff/finances.org")
                "|%(org-read-date)| %^{Description}| %^{Amount}| %^{Account}|")))
                

## How does it works
So, by pressing 'f' you can active the template. It will ask you 4 variables to store one transaction in the `finances.org` file:

1. date
2. description
3. amount of money
4. the account the money goes/come

As an example:

    2016-01-01    Barber    -10.00    cash
    

I use `OPENING` as a description for bootstrapping the file.

## Results

Your transactions will be store in an org table, like the following

    |2016-01-01|    OPENING  |   300.00|    cash|
    |2016-01-01|    OPENING  |  1000.00|    bank|
    |2016-01-01|    Barber   |   -10.00|    cash|
    |2016-01-02|    Rent     |  -400.00|    bank|
    |2016-01-03|    Beer     |    -5.00|    cash|
    |2016-01-04|    Job paym.|   700.00|    bank|

## What else?

Since the data are in a matrix form you can do all sort of statistics.

Plans for the future:

1. make it compatible with ledger
2. write a function to compute summary statistics
3. display a nice report

