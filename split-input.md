
import React from 'react';
import styled from 'styled-components';

const Container = styled.div`
  display: flex;
  align-items: center;
`;

const Select = styled.select`
  width: 100%;
  padding: 8px;
  border-radius: 4px 0 0 4px;
  border: 1px solid #ccc;
  appearance: none;
  background-color: #fff;
`;

const TextField = styled.input`
  flex-grow: 1;
  padding: 8px;
  border-radius: 0 4px 4px 0;
  border: 1px solid #ccc;
`;

const SplitInput = ({ options, value, onChange }) => {
  return (
    <Container>
      <Select value={value} onChange={onChange}>
        {options.map((option) => (
          <option key={option.value} value={option.value}>
            {option.label}
          </option>
        ))}
      </Select>
      <TextField type="text" />
    </Container>
  );
};

export default SplitInput;




import React from 'react';
import SplitInput from './SplitInput';

const options = [
  { label: 'Option 1', value: 'option1' },
  { label: 'Option 2', value: 'option2' },
  { label: 'Option 3', value: 'option3' },
];

const App = () => {
  const handleChange = (event) => {
    console.log(event.target.value);
  };

  return (
    <div>
      <SplitInput options={options} onChange={handleChange} />
    </div>
  );
};

export default App;

