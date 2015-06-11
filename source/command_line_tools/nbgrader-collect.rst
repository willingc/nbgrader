``nbgrader collect``
========================

::

    Collect an assignment from the nbgrader exchange
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --update
        Update existing submissions with ones that have newer timestamps.
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
    
        Collect assignments students have submitted. For the usage of instructors.
        
        This command is run from the top-level nbgrader folder. Before running
        this command, you must set the unique `course_id` for the course. It must be
        unique for each instructor/course combination. To set it in the config
        file add a line to the `nbgrader_config.py` file:
        
            c.NbGraderConfig.course_id = 'phys101'
        
        To pass the `course_id` at the command line, add `--course=phys101` to any
        of the below commands.
        
        To collect `assignment1` for all students:
        
            nbgrader collect assignment1
        
        To collect `assignment1` for only `student1`:
        
            nbgrader collect --student=student1 assignment1
        
        Collected assignments will go into the `submitted` folder with the proper
        directory structure to start grading. All submissions are timestamped and
        students can turn an assignment in multiple times. The `collect` command
        will always get the most recent submission from each student, but it will
        never overwrite an existing submission unless you provide the `--update`
        flag:
        
            nbgrader collect --update assignment1
    
    