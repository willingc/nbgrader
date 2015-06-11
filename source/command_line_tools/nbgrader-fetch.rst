``nbgrader fetch``
========================

::

    Fetch an assignment from the nbgrader exchange
    
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
    
        Fetch an assignment that an instructor has released. For the usage of students.
        
        You can run this command from any directory, but usually, you will have a
        directory where you are keeping your course assignments.
        
        To fetch an assignment you must first know the `course_id` for your course.
        If you don't know it, ask your instructor.
        
        To show the list of assignments available for fetching (assume the `course_id`
        is `phys101`):
        
            nbgrader list phys101
        
        To fetch an assignment by name into the current directory:
        
            nbgrader fetch phys101 assignment1
        
        This will create an new directory named `assignment1` where you can work
        on the assignment. When you are done, use the `nbgrader submit` command
        to turn in the assignment.
    
    