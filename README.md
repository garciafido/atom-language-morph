# language-morph

name: 'Morph'
scopeName: 'source.morph'
type: 'tree-sitter'
parser: 'tree-sitter-morph'
fileTypes: ['morph']

scopes:
     'program': 'source.morph'

     '"function"': 'storage.type.function'
     '"=>"': 'storage.type.function.arrow'

      'comment': 'comment.block'

      'import > "from"': 'keyword.control'
      'import > "import"': 'keyword.control'

      'class > "class"': 'support.storage.type'
      'class > "extends"': 'storage.modifier'
      'class > "abstract"': 'storage.modifier'

      'newclass > "newclass"': 'support.storage.type'

      '"function"': 'storage.type.function'
      '"=>"': 'storage.type.function.arrow'

      'enum_definition > "enum"': 'keyword.modifier'

      'constant_declaration > "const"': 'storage.modifier'

      'foreach_function > "foreach"': 'keyword.control'
      'if_function > "if"': 'keyword.control'

      'decorator > decorator_identifier': 'variable.other.object.property'

      'function_call > identifier': 'entity.name.function'

      'identifier > camel_identifier': 'variable.other.object.property'
      'identifier > snake_identifier': 'variable.other.object.property'
      'identifier > pascal_identifier': 'variable.other.object.property'

      'simple_string': 'string.quoted.double'
      'template_string': 'string.quoted.template'
      'escape_sequence': 'constant.character.escape'
      'template_substitution': 'constant.other.rune'

      'integer': 'constant.numeric.integer'
      'float': 'constant.numeric.float'
      'False': 'constant.language.false'
      'True': 'constant.language.true'

      '"in"': 'keyword.control'

      '":"': 'keyword.operator'
      '"+"': 'keyword.operator'
      '"-"': 'keyword.operator'
      '"*"': 'keyword.operator'
      '"/"': 'keyword.operator'
      '"%"': 'keyword.operator'
      '"=="': 'keyword.operator'
      '"!="': 'keyword.operator'
      '">"': 'keyword.operator'
      '"<"': 'keyword.operator'
      '">="': 'keyword.operator'
      '"<="': 'keyword.operator'
      '"!"': 'keyword.operator'
      '"|"': 'keyword.operator'
      '"&"': 'keyword.operator'
      '"||"': 'keyword.operator'
      '"&&"': 'keyword.operator'

folds: [
    {
        type: 'comment'
    }
    {
        start: {index: 0, type: '{'}
        end: {index: -1, type: '}'}
    }
    {
        start: {index: 0, type: '['}
        end: {index: -1, type: ']'}
    }
    {
        start: {index: 0, type: '('}
        end: {index: -1, type: ')'}
    }
]

comments: [
    {
        start: '/* '
        end: ' */'
    }

    {
        start: '// '
    }
]

