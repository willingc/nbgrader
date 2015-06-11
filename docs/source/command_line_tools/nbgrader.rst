``nbgrader``
========================

::

    A system for assigning and grading notebooks
    
    Subcommands
    -----------
    
    Subcommands are launched as `nbgrader cmd [args]`. For information on using
    subcommand 'cmd', do: `nbgrader cmd -h`.
    
    formgrade
        Manually grade assignments (after autograding). Intended for use
        by instructors only.
    release
        Release an assignment to students through the nbgrader exchange.
        Intended for use by instructors only.
    submit
        Submit an assignment to an instructor through the nbgrader exchange.
        Intended for use by students only.
    assign
        Create the student version of an assignment. Intended for use by
        instructors only.
    list
        List inbound or outbound assignments in the nbgrader exchange.
        Intended for use by instructors and students.
    autograde
        Autograde submitted assignments. Intended for use by instructors
        only.
    extension
        Install and activate the "Create Assignment" notebook extension.
    collect
        Collect an assignment from students through the nbgrader exchange.
        Intended for use by instructors only.
    feedback
        Generate feedback (after autograding and manual grading).
        Intended for use by instructors only.
    validate
        Validate a notebook in an assignment. Intended for use by
        instructors and students.
    fetch
        Fetch an assignment from an instructor through the nbgrader exchange.
        Intended for use by students only.
    
    Options
    -------
    
    Arguments that take values are actually convenience aliases to full
    Configurables, whose aliases are listed on the help line. For more information
    on full configurables, see '--help-all'.
    
    --generate-config
        Generate a config file.
    --overwrite
        Overwrite existing config files.
    --quiet
        set log level to CRITICAL (minimize logging output)
    --debug
        set log level to DEBUG (maximize logging output)
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
    
        The nbgrader application is a system for assigning and grading notebooks.
        Each subcommand of this program corresponds to a different step in the
        grading process. In order to facilitate the grading pipeline, nbgrader
        places some constraints on how the assignments must be structured. By
        default, the directory structure for the assignments must look like this:
        
            {nbgrader_step}/{student_id}/{assignment_id}/{notebook_id}.ipynb
        
        where 'nbgrader_step' is the step in the nbgrader pipeline, 'student_id'
        is the ID of the student, 'assignment_id' is the name of the assignment,
        and 'notebook_id' is the name of the notebook (excluding the extension).
        For example, when running `nbgrader autograde "Problem Set 1"`, the
        autograder will first look for all notebooks for all students in the
        following directories:
        
            submitted/*/Problem Set 1/*.ipynb
        
        and it will write the autograded notebooks to the corresponding directory
        and filename for each notebook and each student:
        
            autograded/{student_id}/Problem Set 1/{notebook_id}.ipynb
        
        These variables, as well as the overall directory structure, can be
        configured through the `NbGraderConfig` class (run `nbgrader --help-all`
        to see these options).
        
        For more details on how each of the subcommands work, please see the help
        for that command (e.g. `nbgrader assign --help-all`).
    
    