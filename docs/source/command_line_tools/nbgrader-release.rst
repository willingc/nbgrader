``nbgrader release``
========================

::

    Release an assignment to the nbgrader exchange
    
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
        Force overwrite of existing files in the exchange.
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
    
        Release an assignment to students. For the usage of instructors.
        
        This command is run from the top-level nbgrader folder. Before running
        this command, there are two things you must do.
        
        First, you have to set the unique `course_id` for the course. It must be
        unique for each instructor/course combination. To set it in the config
        file add a line to the `nbgrader_config.py` file:
        
            c.NbGraderConfig.course_id = 'phys101'
        
        To pass the `course_id` at the command line, add `--course=phys101` to any
        of the below commands.
        
        Second, the assignment to be released but already be in the `release` folder.
        The usual way of getting an assignment into this folder is by running
        `nbgrader assign`.
        
        To release an assignment named `assignment1` run:
        
            nbgrader release assignment1
        
        If the assignment has already been released, you will have to add the
        `--force` flag to overwrite the released assignment:
        
            nbgrader release --force assignment1
        
        To query the exchange to see a list of your released assignments:
        
            nbgrader list
    
    