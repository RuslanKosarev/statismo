set( _VTKTests
  PosteriorModelBuilderTest
  PCAModelBuilderWithSelfAdjointEigenSolverTest
  vtkStandardImageRepresenterTest
  vtkStandardMeshRepresenterTest
)

foreach( _test ${_VTKTests} )
  add_executable( ${_test} ${_test}.cxx )
  target_link_libraries( ${_test} statismo_VTK )
endforeach()

add_test( NAME PosteriorModelBuilderTest
  COMMAND PosteriorModelBuilderTest ${statismo_SOURCE_DIR}/data
)
add_test( NAME PCAModelBuilderWithSelfAdjointEigenSolverTest
  COMMAND PCAModelBuilderWithSelfAdjointEigenSolverTest ${statismo_SOURCE_DIR}/data
)
add_test( NAME vtkStandardImageRepresenterTest
  COMMAND vtkStandardImageRepresenterTest ${statismo_SOURCE_DIR}/data
)
add_test( NAME vtkStandardMeshRepresenterTest
  COMMAND vtkStandardMeshRepresenterTest ${statismo_SOURCE_DIR}/data
)
