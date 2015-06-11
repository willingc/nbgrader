``nbgrader list``
========================

::

    List assignments in the nbgrader exchange
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --inbound
        List inbound files rather than outbound.
    --remove
        Remove an assignment from the exchange.
    --debug
        set log level to DEBUG (maximize logging output)
    --quiet
        set log level to CRITICAL (minimize logging output)
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
    --config=<Unicode> (BasicConfig.extra_config_file)
        Default: ''
        Path to an extra config file to load. If specified, load this config file in
        addition to any other IPython config.
    --assignment=<Unicode> (NbGraderConfig.assignment_id)
        Default: ''
        The assignment name. This MUST be specified, either by setting the config
        option, passing an argument on the command line, or using the --assignment
        option on the command line.
    --timezone=<Unicode> (TransferApp.timezone)
        Default: 'UTC'
        Timezone for recording timestamps
    --course=<Unicode> (NbGraderConfig.course_id)
        Default: ''
        A key that is unique per instructor and course. This MUST be specified,
        either by setting the config option, or using the --course option on the
        command line.
    --notebook=<Unicode> (NbGraderConfig.notebook_id)
        Default: '*'
        File glob to match notebook names, excluding the '.ipynb' extension. This
        can be changed to filter by notebook.
    
    To see all available configurables, use `--help-all`
    
    Examples
    --------
    
        List assignments in the nbgrader exchange. For the usage of instructors
        and students.
        
        Students
        ========
        
        To list assignments for a course, you must first know the `course_id` for
        your course. If you don't know it, ask your instructor.
        
        To list the released assignments for the course `phys101`:
        
            nbgrader list phys101
        
        Instructors
        ===========
        
        To list outbound (released) or inbound (submitted) assignments for a course,
        you must configure the `course_id` in your config file or the command line.
        
        To see all of the released assignments, run
        
            nbgrader list  # course_id in the config file
        
        or
        
            nbgrader list phys101  # course_id provided
        
        To see the inbound (submitted) assignments:
        
            nbgrader list --inbound phys101
        
        You can use the `--student` and `--assignment` options to filter the list
        by student or assignment:
        
            nbgrader list --inbound --student=student1 --assignment=assignment1 phys101
        
        If a student has submitted an assignment multiple times, the `list` command
        will show all submissions with their timestamps.
        
        The `list` command can optionally remove listed assignments by providing the
        `--remove` flag:
        
            nbgrader list --inbound --remove --student=student1 phys101
    
    