#######
History
#######

The Iceland release of DART added a powerful and flexible mechanism to
generate the core observation operator code using the *preprocess*
program. The use of the *preprocess* program was covered above in
`Building the Lorenz_63 DART project <#building>`__ and `High-level DA
workflows in DART <#dartWorkflow>`__, so it is assumed you are familiar
with the basic workings of the *preprocess* program before continuing.

To add your own observation support, you will need to create an
*observation definition*. The DART Fortran90 derived type *obs_def*
provides an abstraction of the definition of an observation. At a higher
level, an *observation sequence* (*obs_seq*) is composed of observation
definitions associated with observed values. The basic operations
required to implement an observation definition are an ability to
compute a forward operator given the model state vector, the ability to
read/write the observation definition from/to a file, and a capability
to do a standard input driven interactive definition of the observation
definition.

DART makes a further distinction between specific *observation types*
and generic *quantities*. Essentially, an *observation type* can be
considered to be instrument-specific and the *quantity* is something you
learned about in physics. As an example, ‘RADIOSONDE_TEMPERATURE’ is an
*observation type* of the fundamental *quantity* ‘TEMPERATURE’. The role
of the various obs_def input files is to define the mapping between the
types and quantities, and optionally to provide type-specific processing
routines. Specifying many observation types allows DART to be able to
evaluate some observations and assimilate others - even if the
instruments measure the same *quantity*.

A single obs_def output module is created by the program *preprocess*
from two kinds of input files. First, a DEFAULT obs_def module (normally
called ``DEFAULT_obs_def_mod.F90`` and documented in the
``DARTHOME/observations/forward_operators`` directory) is used as a
template into which the preprocessor incorporates information from zero
or more special obs_def modules (for example,
``obs_def_1d_state_mod.f90`` or ``obs_def_reanalysis_bufr_mod.f90``) as
documented in the ``DARTHOME/observations/forward_operators`` directory.
If no special obs_def files are included in the preprocessor namelist, a
minimal ``obs_def_mod.f90`` is created which can only support identity
forward observation operators.