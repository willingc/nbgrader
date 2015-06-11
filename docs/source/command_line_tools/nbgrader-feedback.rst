``nbgrader feedback``
========================

::

    Generate feedback from a graded notebook
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --force
        Overwrite an assignment/submission if it already exists.
    --student=<Unicode> (NbGraderConfig.student_id)
        Default: '*'
        File glob to match student IDs. This can be changed to filter by student.
        Note: this is always changed to '.' when running `nbgrader assign`, as the
        assign step doesn't have any student ID associated with it.
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --db=<Unicode> (NbGraderConfig.db_url)
        Default: 'sqlite:///gradebook.db'
        URL to the database
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --notebook=<Unicode> (NbGraderConfig.notebook_id)
        Default: '*'
        File glob to match notebook names, excluding the '.ipynb' extension. This
        can be changed to filter by notebook.
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    --assignment=<Unicode> (NbGraderConfig.assignment_id)
        Default: ''
        The assignment name. This MUST be specified, either by setting the config
        option, passing an argument on the command line, or using the --assignment
        option on the command line.
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        Create HTML feedback for students after all the grading is finished.
        This takes a single parameter, which is the assignment ID, and then (by
        default) looks at the following directory structure:
        
            autograded/*/{assignment_id}/*.ipynb
        
        from which it generates feedback the the corresponding directories
        according to:
        
            feedback/{student_id}/{assignment_id}/{notebook_id}.html
        
        Running `nbgrader feedback` requires that `nbgrader autograde` (and most
        likely `nbgrader formgrade`) have been run and that all grading is
        complete.
        
        To generate feedback for all submissions for "Problem Set 1":
            nbgrader feedback "Problem Set 1"
        
        To generate feedback only for the student with ID 'Hacker':
            nbgrader feedback "Problem Set 1" --student Hacker
        
        To feedback for only the notebooks that start with '1':
            nbgrader feedback "Problem Set 1" --notebook "1*"
    
    