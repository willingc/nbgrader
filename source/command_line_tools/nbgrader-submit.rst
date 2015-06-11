``nbgrader submit``
========================

::

    Submit an assignment to the nbgrader exchange
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
    --assignment=<Unicode> (NbGraderConfig.assignment_id)
        Default: ''
        The assignment name. This MUST be specified, either by setting the config
        option, passing an argument on the command line, or using the --assignment
        option on the command line.
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --timezone=<Unicode> (TransferApp.timezone)
        Default: 'UTC'
        Timezone for recording timestamps
    --log-level=<Enum> (Application.log_level)
        Default: 30
        Choices: (0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL')
        Set the log level by value or name.
    --student=<Unicode> (NbGraderConfig.student_id)
        Default: '*'
        File glob to match student IDs. This can be changed to filter by student.
        Note: this is always changed to '.' when running `nbgrader assign`, as the
        assign step doesn't have any student ID associated with it.
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    --db=<Unicode> (NbGraderConfig.db_url)
        Default: 'sqlite:///gradebook.db'
        URL to the database
    --notebook=<Unicode> (NbGraderConfig.notebook_id)
        Default: '*'
        File glob to match notebook names, excluding the '.ipynb' extension. This
        can be changed to filter by notebook.
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        Submit an assignment for grading. For the usage of students.
        
        You must run this command from the directory containing the assignments
        sub-directory. For example, if you want to submit an assignment named
        `assignment1`, that must be a sub-directory of your current working directory.
        If you are inside the `assignment1` directory, it won't work.
        
        To fetch an assignment you must first know the `course_id` for your course.
        If you don't know it, ask your instructor.
        
        To submit `assignment1` to the course `phys101`:
        
            nbgrader submit assignment1 phys101
        
        You can submit an assignment multiple times and the instructor will always
        get the most recent version. Your assignment submission are timestamped
        so instructors can tell when you turned it in. No other students will
        be able to see your submissions.
    
    