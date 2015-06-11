``nbgrader extension``
========================

::

    Utilities for managing the nbgrader extension
    
    Subcommands
    -----------
    
    Subcommands are launched as `nbgrader extension cmd [args]`. For information on
    using subcommand 'cmd', do: `nbgrader extension cmd -h`.
    
    activate
        Activate the extension.
    deactivate
        Deactivate the extension.
    install
        Install the extension.
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    
    To see all available configurables, use `--help-all`
    
    