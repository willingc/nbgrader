``nbgrader validate``
========================

::

    Validate a notebook by running it
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --invert
        Complain when cells pass, rather than vice versa.
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        You can run `nbgrader validate` on just a single file, e.g.:
            nbgrader validate "Problem 1.ipynb"
        
        Or, you can run it on multiple files using shell globs:
            nbgrader validate "Problem Set 1/*.ipynb"
        
        If you want to test instead that none of the tests pass (rather than that
        all of the tests pass, which is the default), you can use --invert:
            nbgrader validate --invert "Problem 1.ipynb"
    
    