``nbgrader autograde``
========================

::

    Autograde a notebook by running it
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --force
        Overwrite an assignment/submission if it already exists.
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --create
        Create an entry for the student in the database, if one does not already exist.
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
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --notebook=<Unicode> (NbGraderConfig.notebook_id)
        Default: '*'
        File glob to match notebook names, excluding the '.ipynb' extension. This
        can be changed to filter by notebook.
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --db=<Unicode> (NbGraderConfig.db_url)
        Default: 'sqlite:///gradebook.db'
        URL to the database
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        Autograde submitted assignments. This takes one argument for the
        assignment id, and then (by default) autogrades assignments from the
        following directory structure:
        
            submitted/*/{assignment_id}/*.ipynb
        
        and saves the autograded files to the corresponding directory in:
        
            autograded/{student_id}/{assignment_id}/{notebook_id}.ipynb
        
        The student IDs must already exist in the database. If they do not, you
        can tell `nbgrader autograde` to add them on the fly by passing the
        --create flag.
        
        Note that the assignment must also be present in the database. If it is
        not, you should first create it using `nbgrader assign`. Then, during
        autograding, the cells that contain tests for the students' answers will
        be overwritten with the master version of the tests that is saved in the
        database (this prevents students from modifying the tests in order to
        improve their score).
        
        To grade all submissions for "Problem Set 1":
        
            nbgrader autograde "Problem Set 1"
        
        To grade only the submission by student with ID 'Hacker':
        
            nbgrader autograde "Problem Set 1" --student Hacker
        
        To grade only the notebooks that start with '1':
        
            nbgrader autograde "Problem Set 1" --notebook "1*"
    
    