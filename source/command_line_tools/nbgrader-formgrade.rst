``nbgrader formgrade``
========================

::

    Grade a notebook using an HTML form
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --student=<Unicode> (NbGraderConfig.student_id)
        Default: '*'
        File glob to match student IDs. This can be changed to filter by student.
        Note: this is always changed to '.' when running `nbgrader assign`, as the
        assign step doesn't have any student ID associated with it.
    --assignment=<Unicode> (NbGraderConfig.assignment_id)
        Default: ''
        The assignment name. This MUST be specified, either by setting the config
        option, passing an argument on the command line, or using the --assignment
        option on the command line.
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    --port=<Int> (FormgradeApp.port)
        Default: 5000
        Port for the server
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --notebook=<Unicode> (NbGraderConfig.notebook_id)
        Default: '*'
        File glob to match notebook names, excluding the '.ipynb' extension. This
        can be changed to filter by notebook.
    --ip=<Unicode> (FormgradeApp.ip)
        Default: 'localhost'
        IP address for the server
    --db=<Unicode> (NbGraderConfig.db_url)
        Default: 'sqlite:///gradebook.db'
        URL to the database
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        Run the formgrader server application in order to manually grade
        submissions that have already been autograded. Running the formgrader
        allows *any* submission (from any assignment, for any student) to be
        graded, as long as it has already been run through the autograder.
        
        By default, the formgrader runs at http://localhost:5000. It also starts
        an IPython notebook server, to allow students' notebooks to be open up
        and run manually if so desired. The notebook server also runs on
        localhost on a random port, though this port can be specified by setting
        `FormgradeApp.nbserver_port`. The notebook server can be disabled entirely
        by setting `FormgradeApp.start_nbserver=False`.
        
        The formgrader must be run from the root of a nbgrader-compatible directory
        structure, which by default looks like:
        
            autograded/{student_id}/{assignment_id}/{notebook_id}.ipynb
        
        To run the formgrader on the default IP and port:
            nbgrader formgrade
        
        To run the formgrader on a public-facing IP address:
            nbgrader formgrade --ip 0.0.0.0
        
        To run the formgrader a different port:
            nbgrader formgrade --port 5001
    
    